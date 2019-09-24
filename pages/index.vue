<template>
    <div>
        <h2>Welcome to the best Corny DadJokes App!</h2>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: 'Home - Dad Jokes',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'best place for the best jokes'
                }
            ]
        }
    },
    mounted() {
        this.$nextTick(() => {
            this.$nuxt.$loading.start()

            setTimeout(() => this.$nuxt.$loading.finish(), 300)
        })
    }
}
</script>

<style>
</style>