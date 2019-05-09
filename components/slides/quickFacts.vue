<template lang="pug">
    section
        h3(class="mt-3") The Writing Systems
        v-layout(align-center justify-center fill-height row wrap v-match-heights="{el: ['.v-card']}")
            v-card(light class="fragment")
                v-layout(align-center justify-center column)
                    v-card-title(class="justify-center") Katakana
                    img(src="@/assets/photos/katakana.png")
            v-card(light class="fragment")
                v-layout(align-center justify-center column)
                    v-card-title(class="justify-center") Hiragana
                    img(src="@/assets/photos/hiragana.png")
            v-card(light class="fragment")
                v-layout(align-center justify-center column)
                    v-card-title(class="justify-center") Kanji
                    img(src="@/assets/photos/kanji.jpg")
</template>

<script>
export default {
    computed: {
        step()
        {
            return this.$parent.$parent.step
        }
    },
    name: "quickfacts",
}
</script>

<style scoped lang="stylus">
*
{
    transition: transform .2s ease-in-out;
}
.v-card
{
    width: 300px;
    margin 10px;
}
h3
{
    // margin-bottom: -40px;
}
</style>
