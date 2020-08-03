<template>
  <div class="container">
      <h2>
        Welcome to the best dad jokes app!
      </h2>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: "Best Dad Jokes",
      meta: [
        {
          content: "Best Dad Jokes app on the Internetz",
          name: "description",
          hid: "description",
        }
      ]
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
