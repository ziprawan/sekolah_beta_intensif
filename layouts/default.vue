<template>
  <div id="app" class="bg-primary">
    <div class="relative min-h-screen flex flex-col justify-between text-xl gap-10 pt-[108px]">
      <WebHeader />

      <div class="px-[20px] md:px-[100px] xl:px-[150px]">
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