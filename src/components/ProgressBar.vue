<template>
  <v-container class="container">
    <v-progress-linear
            :value="progress"
            height="15"
            background-color="grey"
            color="green"
            background-opacity="0.3"
    > {{progress}}
    </v-progress-linear>
  </v-container>
</template>


<script>
  export default {
    props: ['todos'],
    data() {
      return {};
    },
    computed: {
      completedTodo() {
        return this.todos.filter(todo => todo.completed).length;
      },
      progress() {
        return Math.ceil(this.completedTodo / this.todos.length * 100) + "%";
      },
    },
  }
  ;
</script>


<style scoped>
  .container {
    max-width: 500px;

    margin-left: auto;
    margin-right: auto;
  }
</style>>
