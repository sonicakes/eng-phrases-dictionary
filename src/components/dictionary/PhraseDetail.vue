<template>
  <div class="card">
    <img class="card-img-top" src="https://picsum.photos/200/100" alt="Card image cap">
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">{{ description }}</p>
      <p class="card-text"><b>{{ source }}</b></p>
    </div>
  </div>
</template>

<script>
export default {
   props: ['title', 'description', 'source']
}
</script>

<style scoped>

</style>