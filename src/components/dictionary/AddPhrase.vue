<template>
  <div>
    <h3>add a new phrase</h3>

    <form @submit.prevent="addPhrase">
      <div class="form-group">
        <label for="phraseTitle">Phrase title</label>
        <input
          type="text"
          class="form-control"
          id="phraseTitle"
          placeholder="e.g. no worries"
          v-model="title"
        />
      </div>

      <div class="form-group">
        <label for="phraseDescription"
          >Describe the meaning of the phrase.
          <small class="text-muted"
            >If copy/pasted from external source, give credit.</small
          >
        </label>
        <textarea
          class="form-control"
          id="phraseDescription"
          rows="4"
          v-model="description"
          placeholder="all right; fine. (aussie informal - Oxford online dictionary)"
        ></textarea>
      </div>
      <h5>Where was this phrase acquired?</h5>
      <div class="form-group form-check">
        <input
          class="form-check-input"
          type="radio"
          name="sourceAcquired"
          id="audio"
          value="audio"
          v-model="source"
        />
        <label class="form-check-label" for="audio">
          Audio: Heard it (radio, TV, podcasts, conversation etc.)
        </label>
      </div>
      <div class="form-group form-check">
        <input
          class="form-check-input"
          type="radio"
          name="sourceAcquired"
          id="visual"
          value="visual"
          v-model="source"
        />
        <label class="form-check-label" for="visual">
          Visual: Read or seen (book, email, Reddit post, message)
        </label>
      </div>
      <div class="form-group form-check">
        <input
          class="form-check-input"
          type="radio"
          name="sourceAcquired"
          id="translation"
          value="audio"
          v-model="source"
        />
        <label class="form-check-label" for="translation">
          Translation: Had to translate something from native language
        </label>
      </div>
      <div class="form-group">
        <label for="imgUrl">Img url</label>
        <input
          type="url"
          class="form-control"
          id="imgUrl"
          placeholder="https://picsum.photos/200/300"
          v-model="imgLink"
        />
      </div>
      <button type="submit" class="btn btn-primary">Add</button>
    </form>
  </div>
</template>

<script>
// import axios from 'axios';

export default {
  emits: ["added-phrase"],
  methods: {
    addPhrase() {
      // using axios
      this.error = null;
      //   axios
      //     .post(
      //       'https://english-phrases-dictionary-default-rtdb.firebaseio.com/',
      //       {
      //         name: this.enteredName,
      //         rating: this.chosenRating
      //       }
      //     )
      //     .then(function(response) {
      //       console.log(response);
      //       if (response.status === 200) {
      //         ///
      //       } else {
      //         throw new Error('could not save data');
      //       }
      //     })
      //     .catch(error => {
      //       console.log(error);
      //       this.error = error.message;
      //     });

      // this.enteredTitle = "";
      // this.whereAcquired = null;
      // this.description = "";

      //adding to static data list first
      this.$emit("added-phrase", {
        title: this.title,
        description: this.description,
        source: this.source,
        imgLink: this.imgLink,
      });
    },
  },

  data() {
    return {
      title: "",
      source: null,
      description: "",
      imgLink: "",
      error: null,
    };
  },
};
</script>
