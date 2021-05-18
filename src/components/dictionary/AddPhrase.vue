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
          placeholder="e.g. No worries"
        />
      </div>

      <div class="form-group">
        <label for="phraseDescription"
          >Describe the meaning of the phrase. <small class="text-muted">If copy/pasted from external source, give credit.</small> </label
        >
        <textarea
          class="form-control"
          id="phraseDescription"
          rows="3"
        ></textarea>
      </div>
      <div class="form-group">
        <h5>Where was this phrase acquired?</h5>
        <div class="form-check">
          <input
            class="form-check-input"
            type="radio"
            name="source"
            id="audio"
            value="sourceAudio"
            checked
          />
          <label class="form-check-label" for="audio">
            Audio: Heard it (radio, TV, podcasts, conversation etc.)
          </label>
        </div>
        <div class="form-check">
          <input
            class="form-check-input"
            type="radio"
            name="source"
            id="visual"
            value="sourceVisual"
          />
          <label class="form-check-label" for="visual">
            Visual: Read or seen (book, email, Reddit post, message)
          </label>
        </div>
        <div class="form-check">
          <input
            class="form-check-input"
            type="radio"
            name="source"
            id="translation"
            value="sourceTranslation"
          />
          <label class="form-check-label" for="translation">
            Translation: Had to translate something from native language
          </label>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
// import axios from 'axios';

export default {
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
    },
  },

  data() {
    return {
      enteredTitle: "",
      source: null,
      description: "",
      error: null,
    };
  },
};
</script>
