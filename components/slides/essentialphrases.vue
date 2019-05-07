<template>
    <section>
        <section v-for="(phrase, index) in phrases" :key="index">
            <div>
                {{phrase.phrase}}
                <br>
                <p>{{kuroshiro.convert(phrase.phrase)}}</p>
                <br>
                {{phrase.meaning}}
                <br>
            </div>
        </section>
    </section>
</template>

<script async>
import Kuroshiro from 'kuroshiro'
import KuromojiAnalyzer from "kuroshiro-analyzer-kuromoji";

const kuroshiro = new Kuroshiro();

export default {
    async mounted()
    {
        await kuroshiro.init(new KuromojiAnalyzer({dictPath: "/ja-dict"}))
    },
    data()
    {
        return {
            kuroshiro: kuroshiro,
            phrases: [
                {
                    phrase: "ありがとう",
                    phraseRomaji: "",
                    meaning: "Thank You",
                    variations: ["ありがとうございます。", "ありがとうございました。"]
                }
            ]
        }
    }
}
</script>

<style>

</style>
