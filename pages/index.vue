<template>
  <v-app style="background: #000000">
    <v-main>
      <v-container>
        <v-row>
          <v-col class="d-flex justify-space-around">
            <h1>DXT FE workshop</h1>
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-carousel
              v-model="model"
              class="rounded-lg"
              color="white"
              show-arrows-on-hover
              delimiter-icon="mdi-minus"
              height="70vh"
            >
              <v-carousel-item v-for="(slide, i) in slides" :key="i" color="white">
                <v-sheet color="white" height="100%" tile class="pa-8">
                  <nuxt-content :document="slide" />
                </v-sheet>
              </v-carousel-item>
            </v-carousel>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>
<script>
export default {
  name: 'IndexPage',
  async asyncData ({ $content }) {
    const slides = await $content('slides').sortBy('slide').fetch()
    return { slides }
  },
  data: () => {
    return {
      model: 0
    }
  }
}
</script>

<style lang="scss">
h1, h2, h3, h4, h5, h6 {
  color: #fe5000;
}

h2 {
  padding-bottom: 1.5em;
}
</style>
