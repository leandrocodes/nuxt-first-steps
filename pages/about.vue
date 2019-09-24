<template>
    <div>
        <h1>About DadJokes</h1>
        <p>This is an app that display corny dadjokes</p>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: 'About Us - Dad Jokes',
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