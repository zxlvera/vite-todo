<template>
  <Todos/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Todos from './components/TodoList.vue'

export default defineComponent({
  name: 'App',
  components: {
    Todos
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #E6F4F1;
  margin-top: 60px;
}
</style>
