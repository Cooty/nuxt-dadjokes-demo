<template>
  <form @submit.prevent="onSubmit">
    <input type="search" v-model="query" aria-label="search jokes" placeholder="Search Jokes..." />
    <button type="submit">Search</button>
  </form>
</template>

<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      query: ""
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.query);
      this.query = "";
    }
  }
}
</script>

<style scoped>

</style>
