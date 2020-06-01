<template>
  <section class="bob">
    <BobCharacter :getRandomInt="getRandomInt" :makeTalk="makeTalk" />
  </section>
</template>

<script>
  import BobCharacter from './BobCharacter.vue'

  export default {
    name: 'BobStage',
    props: {
      getRandomInt: Function,
      makeTalk: Boolean
    },
    components: {
      BobCharacter
    }
  };

</script>

<style scoped>
  .bob {

  }
</style>