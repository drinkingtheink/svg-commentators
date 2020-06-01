<template>
  <main v-on:keyup.enter="captureEnter">
    <BaseballBoard />
    <p class="control-info" :class="{ hidden: makeTalk }">
      You can make them talk by hitting 'Enter'
    </p>
    
    <section class="commentators-stage">
      <BobStage :getRandomInt="getRandomInt" :makeTalk="makeTalk" />
      <HarryStage :getRandomInt="getRandomInt" :makeTalk="makeTalk" />
    </section>
  </main>
</template>

<script>
import BobStage from './BobStage.vue'
import HarryStage from './HarryStage.vue'
import BaseballBoard from './BaseballBoard.vue'

export default {
  name: 'AppStage',
  components: {
    BobStage,
    HarryStage,
    BaseballBoard
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
  main {
    position: relative;
  }

  .control-info {
    margin: 0;
    padding: .5em;
    text-align: center;
    background-color: rgba(0,0,0, 0.4);
    color: white;
    transition: all .2s;
    margin-bottom: 1em;
    opacity: 1;
    font-weight: bold;
    position: static;
    z-index: 1;
  }

  .control-info.hidden {
    opacity: 0;
  }

  .commentators-stage {
    display: flex;
    justify-content: space-around;
  }
</style>
