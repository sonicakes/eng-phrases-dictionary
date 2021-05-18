<template>
  <div id="app">
    <div class="container">
      <div class="row">
        <div class="col">
          <div class="alert alert-success" role="alert" v-if="added">
            Successfully added a new phrase!
            <button
              type="button"
              class="close"
              data-dismiss="alert"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <AddPhrase @added-phrase="phraseAdd" />
          <PhrasesList :phrases="phrases" />
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
      added: false,
      phrases: [
        {
          title: "Beat around the bush",
          description:
            "to avoid talking about what is important (Cambridge dictionary online)",
          source: "visual",
          imgLink:
            "https://images.unsplash.com/photo-1508138221679-760a23a2285b?ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8cmFuZG9tfGVufDB8fDB8fA%3D%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=700&q=60",
        },
        {
          title: "Go the extra mile",
          description:
            "make a special effort to achieve something (Oxford dictionary online)",
          source: "audio",
          imgLink:
            "https://randomwordgenerator.com/img/picture-generator/52e3d541435ba814f1dc8460962e33791c3ad6e04e5074417c2e7dd29045c2_640.jpg",
        },
        {
          title: "When pigs fly",
          description: "something that will never happen (theidioms.com)",
          source: "translation",
          imgLink:
            "https://64.media.tumblr.com/47d1f45f3e4a26fc3e6b5c9720f1425e/tumblr_pbmex4OSWn1wa7o90o1_1280.jpg",
        },
      ],
    };
  },
  methods: {
    phraseAdd(phrase) {
      this.added = true;
      setTimeout(() => (this.added = false), 3000);
      const newPhrase = {
        title: phrase.title,
        description: phrase.description,
        source: phrase.source,
        imgLink: phrase.imgLink,
        id: new Date().toISOString(),
      };
      this.phrases.unshift(newPhrase);
      console.log(newPhrase);
    },
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
