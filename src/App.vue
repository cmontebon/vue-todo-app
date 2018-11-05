<template>
  <div id="app">
    <h1>VueJS To-Do App</h1>
    <img src="./assets/logo.png">
    <todo-list></todo-list>
  </div>
</template>

<script>
import TodoList from './components/todolist'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 750px;
  margin:auto;
  padding: 20px;
  height:750px;
  background-color: #fff;
}

body {
  background-color: #4ac08e;
}
</style>
