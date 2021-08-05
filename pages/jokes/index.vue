<template>
    <div>
      <search-jokes @searchText= 'onSearchText'></search-jokes>
      <joke v-for="joke in jokes" :key="joke.id"
        :id="joke.id" :joke="joke.joke"> </joke>
    </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue';
import SearchJokes from '../../components/SearchJokes.vue';
export default {
  components: {Joke, SearchJokes  },
  data() {
    return { jokes: [] };
  },
  async created() {
    const H = {
      headers: {Accept: 'application/json'}
    };
    try {
      const response = await axios.get('https://icanhazdadjoke.com/search', H);
      this.jokes = response.data.results;
      
    } catch (err) {
      console.log(err);
    }
    
  },
  methods: {
    async onSearchText(text) {
      const H = {
      headers: {Accept: 'application/json'}
      };
    try {
      const response = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, H);
      this.jokes = response.data.results;
      
    } catch (err) {
      console.log(err);
    }
    }
  },
  head() {
    return {
      title: "jokes",
      meta: [ { hid: 'description', name: 'description',content: 'This is an jokes site'}]
    };
  }       
}
</script>

<style scoped>

</style>