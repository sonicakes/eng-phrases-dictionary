<template>
  <div class="card">
    <img
      class="card-img-top"
      v-bind:src="imgUrl"
      alt="Image related to the phrase"
    />
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">{{ description }}</p>
      <p class="card-text">
        source:
        <b>{{ source }}</b>
      </p>
      <p class="muted">
        Added on <i>{{ date }}</i>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["title", "description", "source", "imgUrl", "date"],
};
</script>

<style scoped></style>
