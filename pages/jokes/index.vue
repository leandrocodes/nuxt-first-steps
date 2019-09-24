<template>
  <div>
    <Joke v-for="i in jokes" :key="i.id" :id="i.id" :joke="i.joke"/>
  </div>
</template>

<script>
import axios from 'axios'
import Joke from '../../components/Joke'
export default {
  components:{
    Joke
  },
  data() {
    return {
      jokes: []
    }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }

    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      //console.log(res.data.results)
      this.jokes = res.data.results
    } catch (error) {
      console.log(error)
    }
  },
  head() {
    return {
      title: 'Jokes List - Dad Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'best place for the best jokes'
        }
      ]
    }
  }
}
</script>

<style>
</style>