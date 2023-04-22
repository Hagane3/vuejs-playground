<script>
import Todo from "./components/Todo.vue";
import PublicApis from "./components/PublicApis.vue";
export default {
  components: {
    Todo,
    PublicApis,
  },
};
</script>

<template>
  <div class="app-container">
    <Todo />
    <PublicApis />
  </div>
</template>

<style scoped>
.app-container {
  display: flex;
  background-color: lightgray;
}
</style>
