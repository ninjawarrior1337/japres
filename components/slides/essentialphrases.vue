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
                    <Promised :promise="$kuroshiro.convert(phrase.phrase, {to: 'romaji', mode: 'spaced'})">
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
                <br v-if="phrase.variations"/>
                <br v-if="phrase.variations"/>
                <p v-if="phrase.variations">
                    <ul>
                        <li v-for="variation in phrase.variations" :key="variation">{{variation}}</li>
                    </ul>
                </p>
            </div>
        </section>
    </section>
</template>

<script async>
import phrases from "@/assets/data/phrases.json"



import { Promised } from 'vue-promised'

export default {
    components: {
        Promised
    },
    data()
    {
        return {
            phrases: phrases
        }
    }
}
</script>

<style>

</style>
