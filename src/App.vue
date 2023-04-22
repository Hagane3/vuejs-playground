<script>
import Todo from "./components/Todo.vue";
import PublicApis from "./components/PublicApis.vue";
import Display from "./components/Display.vue";
export default {
  components: {
    Todo,
    PublicApis,
    Display,
  },
  data() {
    return {
      title: "Vue Playground",
    };
  },
  methods: {
    changeTitle(e) {
      this.title = e.target.value;
    },
  },
};
</script>

<template>
  <div class="app">
    <h1>{{ title }}</h1>
    <div class="app-container">
      <Todo />
      <PublicApis />
      <Display />
    </div>
    <div class="change-title-container">
      <p>change title</p>
      <input v-model="title" @input="changeTitle" />
    </div>
  </div>
</template>

<style scoped>
.app {
  text-align: center;
}

h1 {
  margin-bottom: 2em;
}
.app-container {
  display: flex;
  justify-content: center;
}

.change-title-container > input {
  width: 50%;
  margin-top: 2em;
}
</style>
