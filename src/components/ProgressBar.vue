<template>
  <v-container class="container">
    <v-progress-linear height="30" value="50%"></v-progress-linear>
  </v-container>
</template>


<script>
  export default {
    props: ["todos"],
    data: () => ({}),
    name: "ProgressBar",
    methods: {},
  };
</script>


<style scoped>
  .container {
    max-width: 500px;

    margin-left: auto;
    margin-right: auto;
  }
</style>>
