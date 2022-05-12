<template>
  <main class="container mx-auto swipe">
    <nuxt-content :document="slide" />
  </main>
</template>
<script>
export default {
  async asyncData ({ $content, params }) {
    const slide = await $content(`slides/${params.slug}`).fetch()
    return { slide }
  }
}
</script>
