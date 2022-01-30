<template>
  <div>
    <h1>Here the jokes</h1>
    <Joke v-for="joke in jokes" :key="joke.id" :joke="joke.joke" :id="joke.id"/>
  </div>
</template>

<script>
import axios from 'axios';
import Joke from '../../components/Joke.vue';

export default {
  components: {
    Joke
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

      // console.log(res.data);

      this.jokes = res.data.results;
      console.log(this.jokes);
    } catch (err) {
      console.log(err)
    }
  },
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
  }
}
</script>

<style>

</style>
