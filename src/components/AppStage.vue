<template>
  <main>
    <h1>SVG Commentators</h1>
    <section class="commentators-stage">
      <BobStage />
      <HarryStage />
    </section>
  </main>
</template>

<script>
import BobStage from './BobStage.vue'
import HarryStage from './HarryStage.vue'

export default {
  name: 'AppStage',
  props: {
    msg: String
  },
  components: {
    BobStage,
    HarryStage
  }
};
</script>

<style scoped>
.commentators-stage {
  display: flex;
  justify-content: space-around;
}
</style>
