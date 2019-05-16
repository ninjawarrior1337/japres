<template lang="pug">
    section
        v-layout(align-center justify-center column fill-height)
            h3 Basic Japanese In ≈10 minutes
            ruby 日本語
                rt にほんご
            br
            h5
                |Created With 
                span
                    img(height=50 src='https://cultofthepartyparrot.com/flags/hd/japanparrot.gif')
                | and
                span
                    img(height=40 src="https://vuejs.org/images/logo.png")
                | By Tyler Rothleder
</template>

<script>
export default {
    name: "intro",
}
</script>

<style lang="stylus" scoped>

</style>
