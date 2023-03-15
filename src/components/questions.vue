<script setup>
import q from "../data/quizes.json"
import {ref, computed} from 'vue'
const emit = defineEmits(['show-result'])
const questions = ref(q)

const quizCompleted = ref(false)
const currentQuestion = ref(0)
let count =   0
const score = computed(()=>{

 let value = 0

 questions.value.forEach(q=>{
   if(q.selected == q.answer){
     value++
   }
 })
 return value

})

const getCurrentQuestion = computed(() => {
 let question = questions.value[currentQuestion.value]
 question.index = currentQuestion.value
 return question
})
// const getCurrentQuestion = computed(() => {
//   const randomIndex = Math.floor(Math.random() * questions.value.length)
//   let question = questions.value[randomIndex]
//   question.index = randomIndex
//   return question
// })
const setAnswer = e => {
 questions.value[currentQuestion.value].selected = e.target.value
 e.target.value = null
}
const nextQuestion = () =>{
 count++
 if(currentQuestion.value< questions.value.length -1){
   currentQuestion.value++
 }else{
   quizCompleted.value = true
 }
}
const showresult = ()=>{
  quizCompleted.value=true
  emit('show-result',{score:score.value,length:questions.value.length})

}
</script> 

<template>
<main class="app">
 <h1>PHP Quiz</h1>
 <section class="quiz" v-if="!quizCompleted">
   <div class="quiz-info">
     <span class="question"> {{ getCurrentQuestion.question }} </span>
     <span class="score"> {{ count }} / {{ questions.length }} </span>
     </div>
     <div class="options">
       <label v-for="(option, index) in getCurrentQuestion.options" :key="index"
             :class="`option ${
               getCurrentQuestion.selected == index 
               ? index == getCurrentQuestion.answer
               ?'correct'
               :'wrong'
               :''
               }${
                   getCurrentQuestion.selected !=null &&
                   index!=getCurrentQuestion.selected?'disabled'
                   :''
               }`">
         <input type="radio" :name="getCurrentQuestion.index" 
               :value="index"
               v-model="getCurrentQuestion.selected"
               :disabled="getCurrentQuestion.selected"
               @click="setAnswer">
               <span> {{ option }} </span>
       </label>
     </div>
     <button v-if="getCurrentQuestion.index != questions.length - 1" @click="nextQuestion"  :disabled="!getCurrentQuestion.selected">Next</button>
     <button v-else @click="showresult">Get result</button>
 </section>
 
</main>
</template>

<style >

.app{
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
  margin-top: 80%;
}
h1{
  font-size: 2rem;
  margin-bottom: 2rem;
}
.quiz{
  background-color: rgb(203, 161, 243);
  padding: 1rem;
  width:100% ;
  max-width:640px ;
  border-radius: 0.5rem;
}
 .quiz-info{
  display: flex;
  justify-content:space-between ;
  margin-bottom: 1rem;
}

.quiz-info .question{
  color:rgb(254, 254, 252);
  font-size:1.5rem ;
}

.quiz-info .score{
  color: rgb(212, 11, 169);
  font-size: 1.25rem;
}

.option{
  display: block;
  padding: 1rem;
  background-color: rgb(78, 50, 90);
  color: aliceblue;
  margin-bottom: 0.5rem;
  border-radius: 0.5rem;
  cursor: pointer;
}
 
.option:hover{
  background-color: rgb(153, 50, 197);
}
.option .correct{
  background-color: #2cce7d;
}
.optiion .wrong{
  background-color: #ff5a5f;
  
}
.option:last-of-type{
  margin-bottom: 0;
}
.option.disabled{
  opacity: 0.5;
}
.option input{
  display: none;
}
</style>
