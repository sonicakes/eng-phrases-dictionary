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
export default {
  props: ["phrases"],
  mounted() {
    // this.loadExperiences();
  },
  components: {
    PhraseDetail,
  },
  data() {
    return {
      error: null,
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
