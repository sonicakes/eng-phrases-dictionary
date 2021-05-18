<template>
  <section class="phrases-list">
    <h3>List of added phrases</h3>
    <div class="card-deck">
      <PhraseDetail
        v-for="phrase in phrases"
        :key="phrase.id"
        :title="phrase.title"
        :description="phrase.description"
        :source="phrase.source"
        :imgUrl="phrase.imgLink"
      ></PhraseDetail>
    </div>
  </section>
</template>

<script>
import PhraseDetail from "./PhraseDetail";
import axios from "axios";

export default {
  mounted() {
    this.loadPhrases();
  },
  components: {
    PhraseDetail,
  },
  props: ["refresh"],
  methods: {
    loadPhrases() {
      this.error = null;
      axios
        .get(
          "https://english-phrases-dictionary-default-rtdb.firebaseio.com/phrases.json"
        )
        .then((response) => {
          if (response.status === 200) {
            return response;
          }
        })

        .then((response) => {
          const results = [];
          for (const id in response.data) {
            results.unshift({
              id: id,
              title: response.data[id].title,
              description: response.data[id].description,
              source: response.data[id].source,
              imgLink: response.data[id].imgLink,
            });
          }
          this.phrases = results;
          this.loadPhrases();
        })

        .catch((error) => {
          console.log(error);
          this.error = "Falied to fetch data - try again later.";
        });
    },
  },
  data() {
    return {
      error: null,
      phrases: [],
    };
  },
};
</script>

<style scoped>
.phrases-list {
  margin-top: 20px;
}

@media (min-width: 576px) {
  .card-deck .card {
    flex: 40%;
    margin-bottom: 20px;
  }
}
</style>
