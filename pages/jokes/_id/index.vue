<template>
    <div>
        <nuxt-link to="/jokes"> Back to Jokes </nuxt-link>
        <p> {{joke}} </p>
        <hr>
        <small>Joke ID: {{$route.params.id}}</small>
    </div>
</template>

<script>
import axios from 'axios';
export default {
    data() {
        return { joke: {} }
    },
    async created() {
        const H = {
      headers: {Accept: 'application/json'}
    };
    try {
      const response = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, H);
      this.joke = response.data.joke;
      console.log(this.joke)
    } catch (err) {
      console.log(err);
    }
    } 
}
</script>

<style scoped>

</style>