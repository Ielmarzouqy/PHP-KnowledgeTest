<script>

export default {
  props:{
    score : String
  }
};
</script>
<template>
  <section >
    <h1>you have finished quiz</h1>
    <span>
      your score is   {{score.score }}/{{ score.length }}
    </span>
  </section>
</template>

<style>

</style>