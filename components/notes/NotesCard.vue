<template>
  <div>
    <a :href="`/notes/${note.id}`">
      <div class="font-sans mt-4 outline outline-1 rounded-md h-36 xl:h-48">
        <div class="w-full px-4 py-2">
          <div class="font-bold text-2xl">{{ note.title }}</div>
          <div class="text-sm text-slate-500">Categories: {{ note.categories.join(", ") }}</div>
          <div class="text-sm text-slate-500 text-justify whitespace-pre-line italic">
            {{ note.content.length > 100 ? `${note.content.slice(0, 97)}...` : note.content }}
          </div>
        </div>
      </div>
    </a>
  </div>
</template>

<script lang="ts">
import type { PropType } from 'vue';

interface Note {
  id: string,
  title: string,
  content: string,
  categories: string[],
  private: boolean
}

export default {
  props: {
    note: {
      type: Object as PropType<Note>,
      required: true
    }
  }
}
</script>