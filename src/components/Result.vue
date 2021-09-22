<template>
  <p>Result is {{score}}ms</p>
  <div v-if="score<500">
      <p>Fast Hand Boi!</p>
  </div>
  <div v-else-if="score>500 && score<700">
      <p>Congrats! Same with me. Just normal person!</p>
  </div>
  <div v-else>
      <p>Try again bitch! So fucking slowwwww!</p>
  </div>
</template>

<script>
export default {
    props:['score']
}
</script>

<style>

</style>