<template>
  <div id="app">
  <div class="section">
    <NoteForm />
  </div>
  <div class="section">
    <NoteList />
  </div>
  </div>
</template>

<script>
import NoteForm from './components/NoteForm.vue';
import NoteList from './components/NoteList.vue';
import './../node_modules/bulma/css/bulma.css';

export default {
  name: 'app',
  components: {
    NoteForm,
    NoteList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
