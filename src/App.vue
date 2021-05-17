<template>
  <div id="app">
   <PhraseDetail />
   <PhraseList />
   <AddPhrase />
  </div>
</template>

<script>
import PhraseDetail from './components/dictionary/PhraseDetail';
import PhraseList from './components/dictionary/PhrasesList';
import AddPhrase from './components/dictionary/AddPhrase';

export default {
  name: 'App',
  components: {
    PhraseDetail,
    PhraseList,
    AddPhrase
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
