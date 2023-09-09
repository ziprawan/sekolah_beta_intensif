<template>
  <div id="app" class="bg-primary">
    <div class="relative min-h-[100vh]">
      <WebHeader />

      <div class="text-xl px-[20px] md:px-[100px] xl:px-[150px] gap-10 pt-[108px] pb-[36px] relative">
        <Nuxt />
      </div>

      <WebFooter />
    </div>
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