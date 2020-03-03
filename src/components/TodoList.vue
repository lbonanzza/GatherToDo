<template>
  <div class="todoItem">
    <ul>
      <v-btn small>
        <v-icon>mdi-sort-alphabetical-descending</v-icon>
      </v-btn>
      <TodoItem
        v-for="todo of todos"
        :key="todo.id + 'label'"
        v-bind:todo="todo"
        @remove-todo="removeTodo"
        @sort="sort"
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
      sort() {
        const str = "Hello";
        this.$emit("sort", str);
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
</style>