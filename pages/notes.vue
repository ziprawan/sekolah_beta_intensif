<template>
  <div>
    <div class="flex justify-between">
      <div>
        Filter category:
        <select id="filter" v-model="filterQuery" class="p-2 rounded-md" name="title">
          <option value="" selected>Select category</option>
          <option 
            v-for="category in Array.from(new Set(notes.filter(n => n.private === privateOnly).flatMap(n => n.categories)))" 
            :key="category"
            :value="category"
          >{{ category }}</option>
        </select>
      </div>
      <div>
        <label for="filterPrivate">Private</label>
        <input id="filterPrivate" type="checkbox" @click="privateOnly=!privateOnly" />
      </div>
    </div>
    <div class="mt-6 mb-2">
      <div v-if="!newNote">
        <button class="bg-slate-300 rounded-lg p-3 font-serif" @click="newNote=!newNote">Add New Note</button>
      </div>
      <div v-else>
        <form @submit.prevent="submitHandler">
          <div class="bg-gray-100 rounded-xl flex flex-col gap-2 py-4 px-6">
            <div class="flex gap-1">
              <p class="text-slate-800">Title:</p>
              <input
                v-model="form.title"
                class="bg-transparent outline outline-1 outline-black w-full"
                autocomplete="off"
                autofocus
                spellcheck="false"
              />
            </div>
            <div class="flex gap-1">
              <p class="text-slate-800">Content:</p>
              <textarea
                v-model="form.content"
                class="text-lg bg-transparent outline outline-1 outline-black w-full"
                autocomplete="off"
                autofocus
                spellcheck="false"
              ></textarea>
            </div>
            <div class="flex gap-1">
              <p class="text-slate-800">Categories:</p>
              <input
                v-model="form.categories"
                class="bg-transparent outline outline-1 outline-black w-full"
                autocomplete="off"
                autofocus
                spellcheck="false"
                placeholder="separated by comma"
              />
            </div>
            <div>
              <input v-model="form.private" type="checkbox" />
              <label>Private</label>
            </div>
            <div class="ml-auto flex gap-4">
              <button type="submit">Save</button>
              <button @click="cancelForm">Cancel</button>
            </div>
          </div>
        </form>
      </div>
    </div>
    <TransitionGroup name="notes" tag="div" class="relative">
      <NotesCard 
        v-for="note in filterNotes" 
        :key="note.id" 
        :note="note" 
      />
    </TransitionGroup>
  </div>
</template>

<script>
import notes from "../assets/notes.json"
import NotesCard from "~/components/notes/NotesCard.vue";

export default {
  components: {
    NotesCard
  },
  data() {
    return {
      notes,
      filterQuery: "",
      privateOnly: false,
      newNote: false,
      form: {
        title: "",
        content: "",
        categories: "",
        private: false
      }
    }
  },
  computed: {
    filterNotes() {
      if (this.filterQuery) {
        return this.notes.filter(note => note.private === this.privateOnly).filter(note => note.categories.includes(this.filterQuery));
      }

      return this.notes.filter(note => note.private === this.privateOnly);
    }
  },
  methods: {
    submitHandler() {
      this.newNote = !this.newNote
      const form = this.form;
      const toAppend = {
        id: "",
        title: form.title.trim(),
        content: form.content.trim(),
        categories: form.categories.trim().trim(",").split(","),
        private: form.private
      };

      this.notes.push(toAppend);
    },
    cancelForm() {
      this.newNote = !this.newNote;
      this.form = {
        title: "",
        content: "",
        categories: "",
        private: false
      };
    }
  }
}
</script>