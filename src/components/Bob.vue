<template>
  <section class="bob">
    <h2>Bob Uecker</h2>
    <BobCharacter />
  </section>
</template>

<script>
  import BobCharacter from './BobCharacter.vue'

  export default {
    name: 'Bob',
    components: {
      BobCharacter
    }
  };

</script>