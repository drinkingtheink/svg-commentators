<template>
  <main v-on:keyup.enter="captureEnter">
    <section class="commentators-stage">
      <BobStage :getRandomInt="getRandomInt" :makeTalk="makeTalk" />
      <HarryStage :getRandomInt="getRandomInt" :makeTalk="makeTalk" />
    </section>
  </main>
</template>

<script>
import BobStage from './BobStage.vue'
import HarryStage from './HarryStage.vue'

export default {
  name: 'AppStage',
  components: {
    BobStage,
    HarryStage
  },
  data() {
    return {
      makeTalk: false
    }
  },
  methods: {
    getRandomInt(min, max) {
      min = Math.ceil(min);
      max = Math.floor(max);
      return Math.floor(Math.random() * (max - min + 1)) + min;
    },
    captureEnter() {
      if(!this.makeTalk) {
        this.makeTalk = true;
      }
    },
    tellThemToTalk() {
      this.makeTalk = true;

      setTimeout(() => {
        this.makeTalk = false;
      }, 2000);
    }
  },
  created() {
    window.addEventListener('keyup', (e) => {
      if (e.keyCode == 13) {
        this.tellThemToTalk();
      }
    });
  },
  beforeDestroy() {
    window.removeEventListener('keyup', null);
  }
};
</script>

<style>
.commentators-stage {
  display: flex;
  justify-content: space-around;
}
</style>
