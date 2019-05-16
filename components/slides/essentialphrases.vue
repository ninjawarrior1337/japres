<template>
    <section>
        <section>
            Common Phrases
        </section>
        <section v-for="(phrase, index) in phrases" :key="index">
            <div>
                {{phrase.phrase}}
                <br>
                <p>
                    <Promised :promise="kuroshiro.convert(phrase.phrase, {to: 'romaji', mode: 'spaced'})">
                        <template v-slot:pending>
                            <p>Loading...</p>
                        </template>
                        <template v-slot="data">
                            <span v-html="data"></span>
                        </template>
                        <template v-slot:rejected>
                            Rejected
                        </template>
                    </Promised>
                </p>
                <br>
                    {{phrase.meaning}}
                <br>
                <br>
                    <p>
                        <ul>
                            <li v-for="variation in phrase.variations">{{variation}}</li>
                        </ul>
                    </p>
            </div>
        </section>
    </section>
</template>

<script async>
import phrases from "@/assets/data/phrases.json"

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
            phrases: phrases
        }
    }
}
</script>

<style>

</style>
