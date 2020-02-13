<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input type="checkbox" v-on:change="todo.completed = !todo.completed">
            <strong>{{todo.id}}</strong>
            {{todo.title}}
        </span>
        <button class="rm">&times;</button>
    </li>
</template>

<script>
  export default {
    props: {
      todo: {
        type: Object,
        required: true
      }
    },
    name: "TodoItem",
  }
</script>

<style scoped>
    li {
        margin-left: auto;
        margin-right: auto;
        width: 500px;
        border: 2px solid #cccccc;
        border-radius: 12px;
        display: flex;
        justify-content: space-between;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }

    .rm {
        background: crimson;
        color: #ffffff;
        border-radius: 7px;
        font-weight: bold;
    }

    input {
        margin-right: 1rem;
    }

    .done {
        text-decoration: line-through;
    }
</style>