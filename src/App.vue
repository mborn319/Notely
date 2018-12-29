<template>
  <div id="app">
  <div class="section">
    <NoteForm v-on:new-note="addNewNote" />
  </div>
  <div class="section">
    <NoteList 
      v-bind:notes="notes"
      v-on:delete-note="deleteNote"
      />
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
  mounted: function() {
    var storedNotes = localStorage.getItem('app-notes');
    if ( storedNotes ) {
      this.notes = JSON.parse( storedNotes );
    }
  },
  methods: {
    addNewNote: function( note ) {
			note.id = Math.random() * 10000000;
      this.notes.push( note );
    },
    deleteNote: function( noteToDelete ) {
      this.notes = this.notes.filter(value => {
        return value.id !== noteToDelete.id;
      });
    }
  },
  watch: {
    notes: function() {
      localStorage.setItem( 'app-notes',JSON.stringify( this.notes ) );
    }
  }
}
</script>

<style>
</style>