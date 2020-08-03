<template>
  <div>
    <nuxt-link to="/jokes">Back to Jokes</nuxt-link>
    <hr/>
    <Joke :joke="joke.joke" :id="joke.id" />
  </div>
</template>

<script>
import axiosConfig from "@/configs/axios-config";
import Joke from "@/components/Joke";

export default {
  name: "JokeById",
  data() {
    return {
      joke: {
        joke: "",
        id: ""
      }
    }
  },
  components: {
    Joke
  },
  async fetch() {
    try {
      const res = await this.$axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, axiosConfig);

      this.joke = res.data;
    } catch(e) {
      console.error(e);
    }
  },
  head() {
    return {
      title: `${this.joke.joke} | ${this.joke.id}`,
      meta: [
        {
          hid: "description",
          name: "description",
          content: `${this.joke.joke}`
        }
      ]
    }
  }
}
</script>
