<template>
  <v-app>
    <div id="app">
      <h1>Todo</h1>
      <hr/>
      <AddTodo @create-todo="createTodo"/>
      <ProgressBar />
      <TodoList class="todo" :todos="todos" @remove-todo="removeTodo" @click="sort"/>
    </div>
  </v-app>
</template>

<script>
  import TodoList from "@/components/TodoList";
  import AddTodo from "@/components/AddTodo";
  import ProgressBar from "@/components/ProgressBar";

  export default {
    name: "App",

    data() {
      return {
        sortableTodos: [],
        todos: [
          {
            id: 1,
            title: "Купить пива",
            completed: false,
          },
          {
            id: 2,
            title: "Купить водки",
            completed: false,
          },
          {
            id: 3,
            title: "Купить сигарет",
            completed: false,
          },
        ],
      };
    },
    methods: {
      removeTodo(id) {
        this.todos = this.todos.filter(t => t.id !== id);
      },
      createTodo(todo) {
        this.todos.push(todo);
      },
      sort() {
        console.log("str");
      },
    },
    components: {
      TodoList,
      AddTodo,
      ProgressBar,
    },
  };
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
