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
      your score is  <span class="score"> {{score.score }}/{{ score.length }}</span>
    </span>
  </section>
</template>

<style>

.result{
  position: absolute;
  width: 100%;
  top: 100px;
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  margin-top: 100rem;
  
}
h1{
  color: rgb(92, 26, 153);
}

.score{
  font-size:x-large;
  padding: 10px;
}
</style>