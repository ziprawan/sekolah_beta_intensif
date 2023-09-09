<template>
  <div>
    <div>
      Filter category:
      <select id="filter" v-model="filterQuery" class="p-1 rounded-md" name="title">
        <option value="" selected></option>
        <option 
          v-for="category in Array.from(new Set(notes.map(n => n.categories).flat()))" 
          :key="category"
          :value="category"
        >{{ category }}</option>
      </select>
    </div>
    <NotesCard v-for="(note, i) in filterNotes" :key="i" :note="note" />
  </div>
</template>

<script lang="ts">
import notes from "../assets/notes.json"
import NotesCard from "~/components/notes/NotesCard.vue";

export default {
  components: {
    NotesCard
  },
  data() {
    return {
      notes,
      filterQuery: ""
    }
  },
  computed: {
    filterNotes() {
      if (this.filterQuery) {
        return this.notes.filter(note => note.categories.includes(this.filterQuery));
      }

      return this.notes;
    }
  }
}
</script>