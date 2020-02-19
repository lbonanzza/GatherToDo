<template>
    <v-app>
        <div id="app">
            <h1>Todo</h1>
            <hr/>
            <AddTodo @create-todo="createTodo"/>
            <ProgerssBar/>
            <TodoList class="todo" v-bind:todos="todos" @removeTodo="removeTodo "/>
        </div>
    </v-app>
</template>

<script>
  import TodoList from "@/components/TodoList";
  import AddTodo from "@/components/AddTodo";
  import ProgerssBar from "@/components/ProgressBar";


  export default {
    name: "App",

    data() {
      return {
        todos: [
          {
            id: 1,
            title: "Купить пива",
            completed: false
          },
          {
            id: 2,
            title: "Купить водки",
            completed: false
          },
          {
            id: 3,
            title: "Купить сигарет",
            completed: false
          }
        ]
      };
    },
    methods: {
      removeTodo(id) {
        this.todos = this.todos.filter(t => t.id != id);
      },
      createTodo(todo) {
        this.todos.push(todo);
      }
    },
    components: {
      TodoList,
      AddTodo,
      ProgerssBar
    }
  };
</script>


<style>
    @import './style.css';
    #app {
        text-align: center;
        margin-top: 60px;
    }

    .todo {
        margin-top: 50px;
    }
</style>
