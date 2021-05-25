<template>
  <div class="todo__card">
  <h1>{{ title }}</h1>
  <input class="todo__input" @keydown.enter="submitTodoItem">
  <TodoListItem v-for="todo in todos" :key="todo.id" :todo="todo"/> 
</div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/runtime-core'
import TodoListItem from './TodoListItem.vue'

export default defineComponent({
  name: 'ToDoList',
  components: {
    TodoListItem
  },
  data() {
    return {
      title: 'Todo List',
      todos: [
      {
        id: 1,
        title: 'Download from Github',
        complete: false
      },
      {
        id: 2,
        title: 'Complete this vue tutorial',
        complete: true
      }
    ]
    }
  }, 
  methods: {
    submitTodoItem(e) {
      this.todos.unshift({
        id: this.todos.length + 1,
        title: e.target.value,
        complete:false
    })
    e.target.value = '';
    }
  }
})

</script>

<style scoped>
.todo__card {
    background: #2E314E;
    display: flex;
    flex-flow: column;
    align-content: center;
    justify-content: space-evenly;
    align-items: center;
    margin: 0 35%;
    border-radius: 8px;
} 

.todo__input {
    width: 80%;
    padding: 0.5rem 0;
    margin-bottom: 1rem;
    border-radius: 8px;
}
</style>
