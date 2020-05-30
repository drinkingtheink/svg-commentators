<template>
  <main>
    <h1>SVG Commentators</h1>
    <section class="commentators-stage">
      <Bob />
      <Harry />
    </section>
  </main>
</template>

<script>
import Bob from './Bob.vue'
import Harry from './Harry.vue'

export default {
  name: 'AppStage',
  props: {
    msg: String
  },
  components: {
    Bob,
    Harry
  }
};
</script>

<style scoped>
.commentators-stage {
  display: flex;
  justify-content: space-around;
}
</style>
