<template>
  <div>
    <h3>add a new phrase</h3>
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
import axios from "axios";

export default {
  methods: {
    addPhrase() {
      // using axios
      this.error = null;
      this.added = true;
      this.removeAlert();
      axios
        .post(
          "https://english-phrases-dictionary-default-rtdb.firebaseio.com/phrases.json",
          {
            title: this.title,
            source: this.source,
            description: this.description,
            imgLink: this.imgLink,
          }
        )
        .then(function(response) {
          console.log(response);
          if (response.status === 200) {
            ///display success alert
          } else {
            throw new Error("could not save data");
          }
        })
        .catch((error) => {
          console.log(error);
          this.error = error.message;
        });

      this.title = "";
      this.source = null;
      this.description = "";
      this.imgLink = "";

      //updating data in the list when the new one is added
      this.$emit("added-phrase");
    },
    removeAlert() {
      setTimeout(() => (this.added = false), 3000);
    },
  },

  data() {
    return {
      title: "",
      source: null,
      description: "",
      imgLink: "",
      error: null,
      added: false,
    };
  },
};
</script>
