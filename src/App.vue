<script>
import HeaderComponent from './components/HeaderComponent.vue'
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent

  },
  data() {
    return {
    }
  },
  props: {},
  methods: {

  }
}
</script>

<template>
  <HeaderComponent />

  <MainComponent />

  <FooterComponent />
</template>

<style lang="scss">
@use "./assets/scss/main.scss" as *;
@use "./assets/scss/reset.scss" as *;
</style>
