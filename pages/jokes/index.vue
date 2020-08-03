<template>
  <div>
    <SearchJokes v-on:search-text="searchText" />
    <nuxt-link v-for="joke in jokes" :to="`jokes/${joke.id}`" :key="joke.id">
      <Joke :id="joke.id" :joke="joke.joke" />
    </nuxt-link>
  </div>
</template>

<script>
import Joke from "@/components/Joke";
import axiosConfig from "@/configs/axios-config";
import SearchJokes from "@/components/SearchJokes";

const searchEndpoint = "https://icanhazdadjoke.com/search";

export default {
  name: "jokes",
  data() {
    return {
      jokes: []
    }
  },
  components: {
    Joke,
    SearchJokes
  },
  async fetch() {
    try {
      const res = await this.$axios.get(searchEndpoint, axiosConfig);

      this.jokes = res.data.results;
    } catch(e) {
      console.error(e);
    }

  },
  head() {
    return {
      title: "Jokes",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "The list of jokes"
        }
      ]
    }
  },
  methods: {
    async searchText(query) {
      try {
        const res = await this.$axios.get(`${searchEndpoint}?term=${query}`, axiosConfig);

        this.jokes = res.data.results;
      } catch(e) {
        console.error(e);
      }
    }
  }
}
</script>
