<script setup>
import Home from './components/Home.vue'
import TodoList from './components/ToDoList.vue'

</script>

<template>
  <header>
    <Home/>
  </header>
  <main>
    <div class="todo-placement">
      <TodoList />
    </div>
  </main>
</template>

<style scoped>
body {
  background-color: aliceblue;
}
</style>
