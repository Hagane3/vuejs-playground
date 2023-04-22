<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
    },
  },
};
</script>
<template>
  <button>{{ text }}</button>
</template>
<style>
button {
  padding: 0.2em 0.4em;
}
</style>
