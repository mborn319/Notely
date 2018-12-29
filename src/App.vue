<template>
  <div id="app">
    <NoteForm />
  </div>
</template>

<script>
import NoteForm from './components/NoteForm.vue';
import './../node_modules/bulma/css/bulma.css';

export default {
  name: 'app',
  components: {
    NoteForm
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
