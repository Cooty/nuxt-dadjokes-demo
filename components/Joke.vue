<template>
  <div class="joke">
    <p>
      {{ joke }}
    </p>
  </div>
</template>

<script>
export default {
  name: "Joke",
  props: {
    joke: {type: String, required: true},
    id: {type: String, required: true},
  }
}
</script>

<style scoped>
  .joke {
    padding: .5rem;
    border: 2px dotted rgba(0, 0, 0, .1);
    margin: 1rem 0;
  }
</style>
