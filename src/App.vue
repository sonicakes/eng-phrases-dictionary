<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col">
          <AddPhrase />
          <PhraseList />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PhraseList from "./components/dictionary/PhrasesList";
import AddPhrase from "./components/dictionary/AddPhrase";

export default {
  name: "App",
  components: {
    PhraseList,
    AddPhrase,
  },
};
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
