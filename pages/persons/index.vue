<template>
  <v-app style="background: #000000">
    <v-main>
      <v-container>
        <v-row class="white">
          <v-col class="d-flex justify-space-around">
            <ul>
              <li v-for="(person, i) in persons" :key="i">
                <router-link :to="'persons/' + person.slug">
                  {{ person.name }}
                </router-link>
              </li>
            </ul>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>
<script>
export default {
  name: 'PersonsPage',
  async asyncData ({ $content }) {
    const persons = await $content('persons').sortBy('date').fetch()
    return { persons }
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
