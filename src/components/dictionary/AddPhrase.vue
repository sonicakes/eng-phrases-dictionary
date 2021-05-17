<template>
    <div>add a new phrase

      <form @submit.prevent="addPhrase">
          <input type="text">
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
    //       '',
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

      this.enteredName = '';
      this.chosenRating = null;
    }

        },
    
     data() {
    return {
      enteredName: '',
      chosenRating: null,
      invalidInput: false,
      error: null
    };
  },
}
</script>