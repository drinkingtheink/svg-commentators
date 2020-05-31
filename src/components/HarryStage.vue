<template>
  <section class="harry">
    <HarryCharacter />
  </section>
</template>

<script>
  import HarryCharacter from './HarryCharacter.vue'

  export default {
    name: 'HarryStage',
    components: {
      HarryCharacter
    }
  };

</script>

<style scoped>
  .harry {
    margin-left: -18em;
  }
</style>