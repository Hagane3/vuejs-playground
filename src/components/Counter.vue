<script>
import ClearCounter from "./ClearCounter.vue";

export default {
  components: {
    ClearCounter,
  },
  props: {
    count: {
      type: Number,
      required: true,
    },
    clearCounter: {
      type: Function,
      required: true,
    },
  },
};
</script>
<template>
  <ClearCounter :clearCounter="clearCounter" />
  <p>Count: {{ count }}</p>
</template>
<style></style>
