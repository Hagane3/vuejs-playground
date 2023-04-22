<script>
import Button from "./Button.vue";
import Counter from "./Counter.vue";
export default {
  components: {
    Button,
    Counter,
  },
  data() {
    return {
      count: 0,
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      this.count--;
    },
    clearCounter() {
      this.count = 0;
    },
  },
};
</script>

<template>
  <div class="container">
    <Counter :count="count" :clearCounter="clearCounter" />
    <div class="buttons">
      <Button text="-" @click="decrement" />
      <Button text="+" @click="increment" />
    </div>
  </div>
</template>

<style>
.container {
  background-color: lightcyan;
  padding: 5em;
  text-align: center;
}

.buttons {
  display: flex;
  justify-content: center;
  gap: 2em;
  margin-top: 1em;
}
</style>
