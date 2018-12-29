<template>
  <div id="app">
  <div class="section">
    <NoteForm
      v-bind:note="form"
      v-on:save-note="saveNote"
      />
  </div>
  <div class="section">
    <NoteList 
      v-bind:notes="notes"
      v-on:delete-note="deleteNote"
      v-on:edit-note="editNote"
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
      notes: [],
      form: {
        title: "",
        body: ""
      }
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
    saveNote: function( note ) {
      if ( note.hasOwnProperty("id") && note.id !== "" ) {
        this.updateExistingNote( note );
      } else {
        this.addNewNote( note );
      }
    },
    updateExistingNote: function( note ) {
      this.notes = this.notes.filter(value => {
        return value.id !== noteToDelete.id;
      });
    },
    addNewNote: function( note ) {
			note.id = Math.random() * 10000000;
      this.notes.push( note );
    },
    deleteNote: function( noteToDelete ) {
      this.notes = this.notes.filter(value => {
        return value.id !== noteToDelete.id;
      });
    },
    editNote: function( noteToEdit ) {
      console.log( noteToEdit, this.form );
      this.form = noteToEdit;
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