<template>
    <div>
        <ul>
            <TodoItem
            v-for="todo of todos"
            :key="todo"
            v-bind:todo="todo"
            />
        </ul>
    </div>
</template>

<script>
  import TodoItem from "./TodoItem"
  export default {
    props: ['todos'],
    name: "TodoList",
    components: {
      TodoItem
    }
  }

</script>

<style scoped>
    ul {
        list-style: none;
        margin: 0;
        padding: 0;
    }
</style>