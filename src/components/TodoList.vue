<template>
  <div class="todoItem">
    <ul class="list">
      <TodoItem
          v-for="todo of todos"
          :key="todo.id + 'label'"
          v-bind:todo="todo"
          @remove-todo="removeTodo"
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
        this.$emit("remove-todo", id);
      },
    },
  };
</script>

<style scoped>
  .todoItem {
    margin-left: auto;
    margin-right: auto;

    max-width: 500px;
  }

  .list {
    padding-left: 0;
  }
</style>