<script>
import Todo from "./components/Todo.vue";
export default {
  components: {
    Todo,
  },
  data() {
    return {
      message: "Hello World!",
      count: 0,
      text: "",
      showApp: true,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      if (this.count > 0) {
        this.count--;
      } else {
        return;
      }
    },
    onInput(e) {
      this.text = e.target.value;
    },
    toggleApp() {
      this.showApp = !this.showApp;
    },
  },
};
</script>

<template>
  <button @click="toggleApp">TOGGLE APP</button>

  <div v-if="showApp" class="container">
    <h1 class="heading">Hello world by Hagane!</h1>
    <h2>{{ message }}</h2>
    <div class="counter">
      <span>{{ count }}</span>
      <div>
        <button @click="increment">INCREASE</button>
        <button @click="decrement">DECREASE</button>
      </div>
    </div>
    <div class="input_display">
      <span>{{ text }}</span>
      <input :value="text" @input="onInput" placeholder="type here" />
    </div>
  </div>
  <h1 v-else>TURN ON APP</h1>
  <Todo />
</template>

<style scoped>
.heading {
  color: red;
}

.container {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.counter {
  text-align: center;
}

.input_display {
  display: flex;
  flex-direction: column;
}
</style>
