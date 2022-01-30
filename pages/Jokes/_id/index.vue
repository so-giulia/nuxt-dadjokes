<template>
  <div>
    <h2>Joke With ID: #{{ $route.params.id }}</h2>
    <p>{{ joke }}</p>

    <nuxt-link to="/jokes" class="back">Back to All Jokes</nuxt-link>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  head(){
    return{
      title: 'Joke id' + this.$route.params.id,
      meta:[
        {
          hid: "description",
          name: "description",
          content: "It's a Nuxt Dad Joke"
        }
      ]
    }
  },
  data(){
    return{
      joke: {}
    }
  },
  async created(){
    const config = {
      headers: {
        'Accept': 'application/json'
      }
    }

    try {
      const res = await axios.get(`https://icanhazdadjoke.com/j/${this.$route.params.id}`, config);

      this.joke = res.data.joke;
      console.log('joke: ', this.joke);
    } catch (err) {
      console.log(err)
    }
  }
}
</script>

<style>
.back{
  display: inline-block;
  margin: 2rem 0;
}

</style>
