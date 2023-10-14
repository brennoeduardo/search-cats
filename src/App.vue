<template>
  <v-app>
    <v-main>
        <TheDog />
    </v-main>
  </v-app>
</template>

<script>
import TheDog from './components/TheDog.vue'

export default {
  name: 'App',

  components: {
    TheDog,
  },

  data: () => ({
    //
  }),
}
</script>
