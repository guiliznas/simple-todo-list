<script setup>
import TodoList from './components/TodoList.vue'
</script>

<template>
  <div>
    Simple To-do List
  </div>
  <div class="full-center">
    <todo-list />
  </div>
</template>

<style>
.full-center {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>

