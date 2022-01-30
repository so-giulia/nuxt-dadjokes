<template>
  <div>
    <h1>Here the jokes</h1>

    <SearchJokes v-on:search-text="searchText" />

    <Joke v-for="joke in jokes" :key="joke.id" :joke="joke.joke" :id="joke.id"/>
  </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue';
import SearchJokes from '../../components/SearchJokes.vue'

export default {
  head(){
    return {
      title: 'The Dad Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'About Nuxt Dad Jokes'
        }
      ]
    }
  },
  components: {
    Joke,
    SearchJokes
  },
  data(){
    return {
      jokes: []
    }
  },
  async created(){
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }

    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config);

      this.jokes = res.data.results;
    } catch (err) {
      console.log(err)
    }
  },
  methods:{
    async searchText(text){
      const config = {
        headers: {
          'Accept': 'application/json'
        }
      }

      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);

        this.jokes = res.data.results;
      } catch (err) {
        console.log(err)
      }
    }
  }
}
</script>

<style>

</style>
