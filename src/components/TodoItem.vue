<template>
  <v-container v-bind:class="{done: todo.completed}">
    <li>
            <span>
                <div>
                    <v-checkbox
                      class="checkbox"
                      v-model="todo.completed"
                      :label="`${todo.title}`"
                    ></v-checkbox>
                </div>

                <v-row class="del-btn" justify="end">
                    <v-dialog v-model="dialog" persistent max-width="290">
                      <template v-slot:activator="{ on }">
                        <v-btn color="error" v-on="on">Del</v-btn>
                      </template>
                      <v-card>
                        <v-card-title class="headline">Уверены, что хотите удалить задачу?</v-card-title>
                        <v-card-actions>
                          <v-spacer></v-spacer>
                          <v-btn color="green darken-1" text @click="dialog = false">Disagree</v-btn>
                          <v-btn color="error" text @click="$emit('remove-todo', todo.id)">Agree</v-btn>
                        </v-card-actions>
                      </v-card>
                    </v-dialog>
                </v-row>

            </span>
    </li>


  </v-container>
</template>


<script>
  export default {
    props: {
      todo: {
        type: Object,
        required: true,
      },
    },
    data() {
      return {
        dialog: false,
      };
    },
    name: "TodoItem",
  };
</script>


<style scoped>

  input {
    margin-right: 1rem;
  }

  li {
    display: flex;
    justify-content: center;
    border: 3px solid #cccccc;
    padding: 5px;
  }

  .done li {
    border: 3px solid chartreuse;
  }

  .checkbox {
    padding-top: 50px;
    padding-right: 50px;
    height: 20px;
    align-items: center;
  }

  .del-btn {
    padding-left: 350px;
  }
</style>












