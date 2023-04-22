<script>
export default {
  props: {
    clearCounter: {
      type: Function,
      required: true,
    },
  },
};
</script>
<template>
  <button @click="clearCounter">Clear Counter</button>
</template>
<style>
button {
  margin-bottom: 2em;
}
</style>
