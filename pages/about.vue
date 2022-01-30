<template>
  <div>
    <h1>About Title</h1>
    <p>page description</p>
  </div>
</template>

<script>
export default {
  name: 'About',
  head(){
    return {
      title: 'About Dad Jokes', // title in browser tab
      meta: [ // meta tags
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
