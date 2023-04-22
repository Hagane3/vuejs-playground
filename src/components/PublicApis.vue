<script>
export default {
  data() {
    return {
      apis: [],
      loading: false,
      error: null,
      startPage: 0,
      endPage: 3,
    };
  },
  methods: {
    async fetchData() {
      const url = "https://api.publicapis.org/entries";
      this.loading = true;
      try {
        const response = await fetch(url);
        const data = await response.json();
        this.apis = data.entries;
      } catch (error) {
        this.error = error;
      } finally {
        this.loading = false;
      }
      console.log(this.apis[0].API);
    },
    nextPage() {
      this.startPage += 3;
      this.endPage += 3;
    },
    prevPage() {
      this.startPage -= 3;
      this.endPage -= 3;
    },
  },
  mounted() {
    this.fetchData();
  },
};
</script>

<template>
  <div class="api-container">
    <p v-if="loading">Loading...</p>
    <div class="public-api" v-for="api in apis.slice(startPage, endPage)">
      <h1>{{ api.API }}</h1>
      <p>{{ api.Description }}</p>
    </div>
    <div class="buttons">
      <button @click="prevPage" :disabled="startPage === 0">
        Previous page
      </button>
      <button @click="nextPage">Next page</button>
    </div>
  </div>
</template>

<style scoped>
.api-container {
  padding: 5em;
  display: flex;
  flex-direction: column;
  gap: 2em;
  background-color: lightgray;
}
.public-api {
  text-align: center;
  border: 1px solid black;
  padding: 1em;
}

.buttons {
  margin: 0 auto;
  display: flex;
  gap: 2em;
}

.buttons > button {
  padding: 0.2em 0.1em;
}
</style>
