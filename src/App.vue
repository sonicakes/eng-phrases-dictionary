<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col">
          <AddPhrase />
          <PhrasesList />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import PhrasesList from "./components/dictionary/PhrasesList";
import AddPhrase from "./components/dictionary/AddPhrase";

export default {
  name: "App",
  components: {
    PhrasesList,
    AddPhrase,
  }
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
