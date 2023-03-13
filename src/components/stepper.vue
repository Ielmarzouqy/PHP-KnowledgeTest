<script setup>
// defineProps({
//   msg: {
//     type: String,
//     required: true
//   }
// })
</script>

<template>
  <div class="container" id="stepper">
     
    <div class="progress-container"> 
        <div class="progress" id="progress"></div>
        <div class="circle active " id="circle">1</div>
        <div class="circle   " id="circle2">2</div>
        <div class="circle " id="circle3">3</div>
    </div>
</div>
</template>

<style scoped>

.progress-container {
  display: flex;
  margin: 0 auto 30px;
  align-items: center;
  justify-content: space-between;
  position: relative;
  width: 350px;
  max-width: 100%;
}
.progress-container::before {
  content: "";
  width: 100%;
  background-color: white;
  height: 5px;
  position: absolute;
  z-index: -1;
}
.progress {
  width: 0;
  background-color: #c3119f;
  height: 5px;
  top: 50%;
  position: absolute;
  transform: translateY(-50%);
  z-index: -1;
  transition: 0.4s ease-in-out;
}

.circle {
  background: #fff;
  height: 30px;
  width: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  border: 3px solid #f1f1f1;
  border-radius: 50px;
}

.active {
  background-color: #c3119f;
  color: #fff;
  transition: 0.6s ease-in;
}
</style>
