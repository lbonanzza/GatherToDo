<template>
  <v-app>
    <div id="app">
      <Header/>
      <AddTodo @create-todo="createTodo"/>
      <ProgerssBar :todos="todos"/>
      <TodoList class="todo" :todos="todos" @remove-todo="removeTodo "/>
    </div>
  </v-app>
</template>

<script>
  import TodoList from "@/components/TodoList";
  import AddTodo from "@/components/AddTodo";
  import ProgerssBar from "@/components/ProgressBar";
  import Header from "@/components/Header";

  export default {
    name: "App",

    data() {
      return {
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
    },
    components: {
      TodoList,
      AddTodo,
      ProgerssBar,
      Header,
    },
  };
</script>


<style>
  .todo {
    margin-top: 30px;
  }
</style>
