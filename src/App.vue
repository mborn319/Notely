<template>
  <div id="app">
  <div class="section">
    <NoteForm />
  </div>
  <div class="section">
    <NoteList v-model="notes" />
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
  }
}
</script>

<style>
</style>