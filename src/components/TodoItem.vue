<template>
    <v-container v-bind:class="{done: todo.completed}">
        <li v-bind:class="{done: todo.completed}">
            <span>
                <div>
                    <v-checkbox
                            class="checkbox"
                            v-model="checkbox2"
                            :label="`${todo.title}`"
                            @change="todo.completed = !todo.completed"
                    ></v-checkbox>
                </div>

                <div class="my-2">
                    <v-btn color="error" @click="$emit('remove-todo', todo.id)">Del</v-btn>
                </div>
            </span>
        </li>


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












