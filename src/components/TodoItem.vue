<template>
    <v-container v-bind:class="{done: todo.completed}">

        <v-card class="mx-auto" max-width="344" outlined :elevation="8">
            <v-list-item three-line>
                <v-list-item-content>
                    <v-list-item-title class="headline mb-1">{{todo.title}}</v-list-item-title>
                </v-list-item-content>
            </v-list-item>

            <v-card-actions>
                <v-btn color="green" text @change="todo.completed = !todo.completed">Done</v-btn>
                <v-btn color="error" text @click="$emit('remove-todo', todo.id)">Delete</v-btn>
            </v-card-actions>
        </v-card>
    </v-container>
</template>


<script>
  export default {
    props: {
      todo: {
        type: Object,
        required: true
      }
    },
    name: "TodoItem"
  };
</script>


<style scoped>

    input {
        margin-right: 1rem;
    }

    .done {
        border: 2px solid;
        border-color: chartreuse;
    }

    .checkbox {
        padding-right: 500px;
        height: 20px;
        align-items: center;
    }
</style>












