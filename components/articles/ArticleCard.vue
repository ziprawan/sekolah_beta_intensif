<template>
  <div
    class="flex flex-col relative bg-slate-100 hover:shadow-2xl hover:bg-slate-50 p-4 md:p-7 rounded-2xl overflow-hidden duration-300 group">
    <div class="relative w-full rounded-lg h-52 content-center overflow-hidden">
      <img :src="article.img" class="object-hover group-hover:scale-110 transition">
    </div>
    <div>
      <div class="font-bold text-slate-950 text-2xl leading-[1.5] my-4">{{ article.title }}</div>
      <div class="text-slate-700 leading-[1.5] mb-5">{{ article.content }}</div>
    </div>
  </div>
</template>

<script lang="ts">
import type { PropType } from 'vue'
interface Article {
  title: string,
  content: string,
  img: string
}

export default {
  props: {
    article: {
      type: Object as PropType<Article>,
      required: true
    }
  }
}
</script>