<template>
  <div>
    <h1>Here the jokes</h1>
  </div>
</template>

<script>
import axios from 'axios'

export default {
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

      console.log(res.data);
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
