<template>
  <picture class="image">
    <img
      :src="src"
      :alt="alt"
      draggable="false"
    >
  </picture>
</template>

<script>
export default {
  name: 'VImg',
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
picture {
  width: 100%;
  height: 100%;
  margin: auto;
  display: flex;
  img {
    width: 100%;
    max-width: 250px;
    height: 100%;
    margin: auto;
    object-fit: contain;
    padding-bottom: 1rem;
  }
}
</style>
