<template lang="pug">
    section
        v-layout(align-center justify-center column fill-height)
            h3 Why Learn Japanese?
            v-layout(align-center justify-center column fill-height)
                p(class="ma-5 fragment") 0. You probably don't speak Japanese now.
                p(class="ma-5 fragment") 1. Audio samples and writing are easy to find.
                div(class="fragment")
                    p(class="ma-5") 2. Japanese is one of the hardest languages to learn next to Arabic and Chinese!
                    p(id="subtitle") Why not challenge yourself?
</template>

<script>
export default {
    name: "whylearn",
}
</script>

<style lang="stylus" scoped>
p
    text-align center

#subtitle
    font-size 20px
    margin-top -20px
</style>

