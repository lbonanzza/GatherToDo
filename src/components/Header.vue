<template>
  <div class="header">
    <div class="header__inner">
      <div class="header-logo">
        <h1>Gather To Do</h1>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Header",
  };
</script>

<style scoped>
  .header {
    width: 100%;
    height: 100px;
    background-color: darkslateblue;

    position: absolute;
    left: 0;
    z-index: 10;
  }

  .header__inner {
    display: flex;
    align-items: center;
    padding: 30px 10px;
  }

  .header-logo {
    color: #ffffff;
  }
</style>