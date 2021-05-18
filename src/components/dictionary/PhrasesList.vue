<template>
   <section>
       <h3>List of added phrases</h3>
    <div class="card-deck">
        <PhraseDetail
          v-for="phrase in phrases"
          :key="phrase.id"
          :title="phrase.title"
          :description="phrase.description"
          :source="phrase.source"
        ></PhraseDetail>
    </div>
   </section>
</template>

<script>
import PhraseDetail from './PhraseDetail';
export default {
    mounted() {
    // this.loadExperiences();
  },
  components : {
PhraseDetail
  },
  data() {
      return {
      phrases: [
          {
              title: 'Beat around the bush',
              description: 'to avoid talking about what is important (Cambridge dictionary online)',
              source: 'visual'
          },
             {
              title: 'Go the extra mile',
              description: 'make a special effort to achieve something (Oxford dictionary online)',
              source: 'audio'
          },
               {
              title: 'When pigs fly',
              description: 'something that will never happen (theidioms.com)',
              source: 'translation'
          },
      ],
      error: null
      }
  }  
}
</script>

<style scoped>
ul {
   list-style-type: none !important;
}
</style>