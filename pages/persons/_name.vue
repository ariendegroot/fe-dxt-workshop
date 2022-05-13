<template>
  <main class="container mx-auto swipe">
    <h1>{{ person.name }}</h1>
    <nuxt-content :document="person" />
  </main>
</template>
<script>
export default {
  async asyncData ({ $content, params }) {
    const person = await $content(`persons/${params.name}`).fetch()
    return { person }
  }
}
</script>
<style>
.img {
    max-width: 200px;
}
</style>
