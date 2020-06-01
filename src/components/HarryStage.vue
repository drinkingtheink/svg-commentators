<template>
  <section class="harry">
    <HarryCharacter :getRandomInt="getRandomInt" :makeTalk="makeTalk" />
  </section>
</template>

<script>
  import HarryCharacter from './HarryCharacter.vue'

  export default {
    name: 'HarryStage',
    props: {
      getRandomInt: Function,
      makeTalk: Boolean
    },
    components: {
      HarryCharacter
    }
  };

</script>

<style scoped>
  .harry {
    margin-left: -18em;
    position: static;
    z-index: 1;
  }
</style>