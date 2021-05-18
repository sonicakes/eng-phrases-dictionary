<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col">
        
          <AddPhrase @added-phrase="phraseAdd"/>
          <PhrasesList :refresh="isRefreshed"/>
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
  },
  data() {
    return {
      isRefreshed: false
      //   {
      //     title: "When pigs fly",
      //     description: "something that will never happen (theidioms.com)",
      //     source: "translation",
      //     imgLink:
      //       "https://64.media.tumblr.com/47d1f45f3e4a26fc3e6b5c9720f1425e/tumblr_pbmex4OSWn1wa7o90o1_1280.jpg",
      //   },
      // ],
    };
  },
  methods: {
    phraseAdd() {
 this.isRefreshed = true;
  }
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
