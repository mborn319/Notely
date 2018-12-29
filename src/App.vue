<template>
  <div id="app">
  <div class="section">
    <NoteForm v-on:new-note="addNewNote" />
  </div>
  <div class="section">
    <NoteList v-bind:notes="notes" />
  </div>
  </div>
</template>

<script>
import NoteForm from './components/NoteForm.vue';
import NoteList from './components/NoteList.vue';
import './../node_modules/bulma/css/bulma.css';

export default {
  name: 'app',
  data: () => {
    return {
      notes: []
    }
  },
  components: {
    NoteForm,
    NoteList
  },
  methods: {
    addNewNote: function( note ) {
      console.log("addNewNote", note);
      this.notes.push( note );
    }
  }
}
</script>

<style>
</style>