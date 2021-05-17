<template>
    <div>phrase list</div>
</template>

<script>
export default {
    mounted() {
    this.loadExperiences();
  },
  data() {
      return {
      results: [],
      isLoading: false,
      error: null
      }
  }  
}
</script>