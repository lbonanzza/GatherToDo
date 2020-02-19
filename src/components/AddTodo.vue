<template>
  <v-container style="max-width: 500px">
    <v-text-field v-model="title" label="What are you working on??" solo @keydown.enter="create"></v-text-field>
  </v-container>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    create() {
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false
        };

        this.$emit("create-todo", newTodo);
        this.title = "";
      }
    }
  }
};
</script>

<style scoped>
  .v-container {
    margin-left: auto;
    margin-right: auto;
  }
</style>>
 