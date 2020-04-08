<template>

  <div>
    <v-app-bar
        color="gray"
        dense
        dark
    >

      <v-toolbar-title>Gather To Do</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-login-variant</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

    </v-app-bar>
  </div>

</template>

<script>
  export default {
    name: "Header",
  };
</script>
