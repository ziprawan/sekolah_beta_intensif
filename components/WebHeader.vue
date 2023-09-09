<template>
  <div
    class="fixed top-0 left-0 w-[100vw] h-[70px] sm:h-[80px] shadow-md lg:px-[100px] md:px-[50px] px-[20px] flex items-center justify-between z-20 bg-slate-50">
    <div class="flex text-xl items-center space-x-5 justify-between">
      <div><a href="/">Home</a></div>
      <div><a href="/notes">Notes</a></div>
      <div><a href="/tools">Tools</a></div>
    </div>
    <!-- <div class="hover:bg-[#FF9000] bg-slate-200 text-slate-900 transition hover:text-white font-semibold px-5 py-3 rounded-full font-poppins">Login</div> -->
    <div class="w-12 h-12 rounded-full overflow-hidden">
      <a href="/profile"><img src="../assets/default.webp" class="object-cover hover:cursor-pointer" /></a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  }
}
</script>