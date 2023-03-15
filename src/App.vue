<script>
import stepper from "./components/stepper.vue"
import questions from "./components/questions.vue"
import result from "./components/result.vue"
import infoPage from './components/infoPage.vue'

export default {
  components: {
    questions,
    stepper,
    result,
    infoPage,
      },
  data() {
    
    return {
      showPage: true,
      currentComponent: infoPage,
      curentStep:1,
      score:null
    };
   

  },
  methods:{
    showQuiz(){
    this.currentComponent = questions
    this.curentStep = 2
    },
    changestepTo3(score){
      // alert(score)
      this.currentComponent = result
      this.score = score
      this.curentStep = 3
     
    }
  }

 
};
</script>
<template>
<component :is="currentComponent" @show-result="changestepTo3" @showQuiz="showQuiz" :score="score"></component>

<stepper :curentStep="curentStep"/>
  
</template>



<style scoped>

*,
*::before,
*::after {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  background-image: linear-gradient(to right, #430D7D 18%, #964185 100%);
  -webkit-animation: transitionIn-Y-bottom 0.5s;
          animation: transitionIn-Y-bottom 0.5s;
  
}
body {
  height: 100vh;
  background: linear-gradient(to right, #430D7D 18%, #471a3e 100%);
}
.start-btn, .res-btn {
  border: none;
  padding: 2px 15px;
  width: 130px;
  height: 60px;
  margin-left: 50px;
  font-size: 20px;
  cursor: pointer;
  color: aliceblue;
  background: #C3119F;
  border-radius: 8px;
}

.infoTitle {
  top: 300px;
  left: 100px;
  color: #C01EA0;
  justify-content: center;
  align-items: center;
  margin-left: 550px;
}

</style>