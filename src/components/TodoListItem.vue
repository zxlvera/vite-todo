<template>
  <div class='todo__item'>
    <div v-if="todo.complete" @click="toggleComplete(todo)">
      <s>{{ todo.title }}</s>
    </div>
    <div v-else @click="toggleComplete(todo)">
      {{ todo.title }}
    </div>
  </div>
</template>
  
<script lang="ts">

export default {
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    toggleComplete(todo: any) {
      todo.complete = !todo.complete
    }
  }
}
</script>

<style>
.todo__item {
    background-image: linear-gradient(120deg, #a1c4fd 0%, #c2e9fb 100%);
    margin-bottom: 1rem;
    padding: 1rem 0 1rem 0;
    width: 80%;
    border-radius: 8px;
    color: #2e314e;
    transition: 0.3s;
}

.todo__item:hover {
    cursor: pointer;
    box-shadow: 2px 2px 8px 0 #c1ebfb;
}
</style>
