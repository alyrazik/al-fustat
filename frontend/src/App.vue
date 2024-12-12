<template>
  <div id="app">
    <h1>Hello Vue.js!</h1>
    <button @click="fetchData">Fetch Data</button>
    <p>{{ message }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "",
    };
  },
  methods: {
    async fetchData() {
      const response = await fetch("http://127.0.0.1:8000/");
      const data = await response.json();
      this.message = data.message;
    },
  },
};
</script>
