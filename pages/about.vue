<template>
  <div>
    <h1>About DadJokes</h1>
    <p>This here is an app that displays terrible jokes</p>
  </div>
</template>

<script>
export default {
  name: "about",
  head() {
    return {
      title: "About the Dad Jokes app",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Best place for corny dad jokes"
        }
      ]
    }

  }
}
</script>

<style scoped>

</style>
