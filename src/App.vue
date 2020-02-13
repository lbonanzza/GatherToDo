<template>
  <div id="app">
    <h1>Gather Todo</h1>
    <hr>
    <TodoList class="todo"
    v-bind:todos="todos"
    />
  </div>
</template>

<script>
import TodoList from "./components/TodoList"

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title: "Купить пива", completed: false},
        {id: 2, title: "Купить водки", completed: false},
        {id: 3, title: "Купить сигарет", completed: false}
      ]
    }
  },
  components: {
    TodoList
  }
}
</script>


<style>
  #app {
    text-align: center;
    margin-top: 60px;
  }

  .todo {
    margin-top: 50px;
  }
</style>