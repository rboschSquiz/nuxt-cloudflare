<template>
  <v-app dark>
    <Header keep-alive/>
    <v-main>
      <v-container>
        <nuxt/>
      </v-container>
    </v-main>
    <Footer/>
  </v-app>
</template>

<script>
import Header from '~/components/Header'
import Footer from '~/components/Footer'

export default {
  components: {
    Header,
    Footer
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="scss">
  .v-application {
    font-family: 'Poppins', sans-serif !important;

    a {
      color: white;
    }
  }
</style>