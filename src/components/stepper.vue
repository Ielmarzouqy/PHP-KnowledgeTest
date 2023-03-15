<script >
export default {
  props: {
    curentStep:String
  },
  data(){
    return{
      steps :3
    }
  }
};
</script>

<template>
  <div class="container" id="stepper">
     
    <div class="progress-container"> 
        <!-- <div class="progress" id="progress"></div> -->
        <div v-for="step in steps" class="circle" :class="{active:  curentStep>=step }" :key="step" id="circle">{{step}}</div>
    </div>
</div>
</template>

<style >
.progress-container {
  display: flex;
  margin: 0 auto 30px;
  align-items: center;
  justify-content: space-between;
  position: relative;
  width: 350px;
  max-width: 100%;
}

.container {
  text-align: center;
  position: absolute;
  top: 1em;
  left: 50%;
  transform: translate(-50%, 18%);
}
.progress-container::before {
  content: "";
  width: 100%;
  background-color: rgb(211, 28, 165);
  height: 5px;
  position: absolute;
  z-index: -1;
}
.progress {
  width: 100px;
  background-color: #cb35ad; 
  height: 5px;
  top: 5%;
  position: absolute;
  transform: translateY(-50%);
  z-index: -1;
  transition: 0.4s ease-in-out;
}*

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
