<template>
  <div class="reveal">
    <div class="slides">
      <intro></intro>
      <why-learn></why-learn>
      <quick-facts></quick-facts>
      <section>
        <hiragana></hiragana>
        <katakana></katakana>
        <kanji></kanji>
      </section>
      <essentialphrases></essentialphrases>
      <grammar></grammar>
      <quizlet-slide></quizlet-slide>
    </div>
  </div>
</template>

<script>
import Reveal from 'reveal.js/js/reveal.js'

import intro from '../components/slides/intro.vue'
import whyLearn from '../components/slides/whyLearn.vue'
import quickFacts from '../components/slides/quickFacts.vue'

import {katakana, hiragana, kanji} from '../components/slides/writingSystems'

import essentialphrases from '../components/slides/essentialphrases.vue'

import grammar from '../components/slides/grammar.vue'
import quizletSlide from '../components/slides/quizlet.vue';

export default {
  mounted()
  {
    Reveal.initialize();
  },
  components: {
    intro,
    whyLearn,
    // TODO add language metadata (statistics / terms)
    quickFacts,
    hiragana,
    katakana,
    kanji,
    essentialphrases,
    grammar,
    quizletSlide
  }
}
</script>

<style>
  @import url('reveal.js/css/reset.css');
  @import url('reveal.js/css/reveal.css');
  @import url('reveal.js/css/theme/black.css');
  .reveal section img
  {
    margin: 0px;
    border: 0px;
    background-color: transparent;
    box-shadow: none;
  }
</style>
