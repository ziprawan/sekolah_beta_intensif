<template>
  <div id="app" class="p-4">
    <WebHeader />

    <Nuxt />

    <WebFooter />
  </div>
</template>

<script>
import WebHeader from "../components/WebHeader.vue"
import WebFooter from "../components/WebFooter.vue"

export default {
  components: {
    WebHeader, WebFooter
  }
}
</script>