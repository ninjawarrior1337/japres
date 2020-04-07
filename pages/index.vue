<template>
  <transition leave-active-class="animated slideOutUp">
    <presentation v-if="loaded"></presentation>
    <div :style="{height: `100vh`}" v-else>
      <v-layout justify-center align-center column fill-height>
        <h1 id="loading">Loading</h1>
        <v-progress-circular indeterminate size="128"></v-progress-circular>
      </v-layout>
    </div>
  </transition>
</template>

<script>
import presentation from "../components/presentation";
import KuromojiAnalyzer from "kuroshiro-analyzer-kuromoji";

export default {
  mounted() {
    this.$kuroshiro
      .init(new KuromojiAnalyzer({ dictPath: "/ja-dict" }))
      .then(() => {
        this.loaded = true;
      })
      .catch(() => {
        this.loaded = true;
      });
  },
  data() {
    return {
      loaded: false
    };
  },
  components: {
    presentation
  }
};
</script>

<style lang="stylus">
@import '~rfs/stylus';
@import "../node_modules/animate.css/animate.css"

#loading {
  margin-bottom: 50px;
  rfs-font-size(128px);
}
</style>
