<template>
    <section>
        <section v-for="(phrase, index) in phrases" :key="index">
            <div>
                {{phrase.phrase}}
                <br>
                <p>
                    <!-- {{kuroshiro.convert(phrase.phrase)}} -->
                    <Promised :promise="kuroshiro.convert(phrase.phrase)">
                        <template v-slot:pending>
                            <p>Loading...</p>
                        </template>
                        <template v-slot="data">
                            <p>{{data}}</p>
                        </template>
                    </Promised>
                </p>
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

import { Promised } from 'vue-promised'

const kuroshiro = new Kuroshiro();

window.kuroshiro = kuroshiro

export default {
    async mounted()
    {
        await kuroshiro.init(new KuromojiAnalyzer({dictPath: "/ja-dict"}))
    },
    components: {
        Promised
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
                },
                {
                    phrase: "ありがとう",
                    phraseRomaji: "",
                    meaning: "Thank You",
                    variations: ["ありがとうございます。", "ありがとうございました。"]
                },
                {
                    phrase: "ありがとう",
                    phraseRomaji: "",
                    meaning: "Thank You",
                    variations: ["ありがとうございます。", "ありがとうございました。"]
                },
            ]
        }
    }
}
</script>

<style>

</style>
