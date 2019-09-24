<template>
    <div>
        <h3>{{ joke }}</h3>
        <small>Joke ID: {{ $route.params.id }}</small>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    data() {
        return {
            joke: {}
        }
    },
    async created() {
        const config = {
            headers: {
                Accept: 'application/json'
            }
        }

        try {
            const res = await axios.get(
                `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
                config
            )
            console.log(res.data.joke)
            this.joke = res.data.joke
            //console.log(joke)
        } catch (error) {
            console.log(error)
        }
    }
}
</script>

<style>
</style>