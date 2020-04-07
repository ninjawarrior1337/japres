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
                    img(height=50 src='https://ppaas.herokuapp.com/partyparrot?overlay=https://cdn.discordapp.com/attachments/407230022743621644/578454411316035585/knadle.png&overlayWidth=13&overlayHeight=20&overlayOffsetX=0&overlayOffsetY=-8')
                | and
                span
                    img(height=40 src="https://vuejs.org/images/logo.png")
                | By Treelar
</template>

<script>
export default {
    name: "intro",
}
</script>

<style lang="stylus" scoped>

</style>
