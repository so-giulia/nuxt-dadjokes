<template>
  <div>
    <h1>Welcome to Dad Jokes</h1>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  head(){
    return {
      title: 'Home | Dad Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Dad Jokes Nuxtjs App'
        }
      ]
    }
  }
}
</script>
