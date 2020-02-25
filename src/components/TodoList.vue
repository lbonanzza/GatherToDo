<template>
  <div class="todoItem">

    <ul class="todo-list">
      <TodoItem
              v-for="todo of todos"
              :key="todo.id + 'label'"
              v-bind:todo="todo"
              @removeTodo="removeTodo"
      />
    </ul>
  </div>
</template>


<script>
  import TodoItem from "./TodoItem";

  export default {
    props: ["todos"],
    name: "TodoList",
    components: {
      TodoItem,
    },
    methods: {
      removeTodo(id) {
        this.$emit("removeTodo", id);
      },
    },
  };
</script>

<style scoped>
  .todo-list {
    padding-left: 0;
  }

  .todoItem {
    margin-left: auto;
    margin-right: auto;

    max-width: 500px;
  }
</style>