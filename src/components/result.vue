<script>

export default {
  props:{
    score : String
  }
};
</script>
<template>
  <section class="result">
    <h1>you have finished quiz</h1>
    <span>
      your score is   {{score.score }}/{{ score.length }}
    </span>
  </section>
</template>

<style>
.result{
 /* margin-top: 40px;*/
  background-color: rgb(187, 127, 243);
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  margin-top: 100rem;
}

</style>