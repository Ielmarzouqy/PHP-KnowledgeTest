<script setup>
import q from "../data/quizes.json"
import {ref, computed} from 'vue'
const questions = ref(q)

const quizCompleted = ref(false)
const currentQuestion = ref(0)
let count =   0


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
</script> 

<template>
<main class="apnp">
 <h1>PHP Quiz</h1>
 <section class="quiz" v-if="!quizCompleted">
   <dev class="quiz-info">
     <span class="question"> {{ getCurrentQuestion.question }} </span>
     <span class="score"> {{ count }} / {{ questions.length }} </span>
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
     <button
     @click="nextQuestion"
     :disabled="!getCurrentQuestion.selected">
     {{ getCurrentQuestion.index == questions.length - 1
         ? 'Finish'
         :getCurrentQuestion.selected == null
         ?'Select an option'
         :'next question'
     }}
     

     </button>
   </dev>
 </section>
 <section v-else>
   <h1>you have finished quiz</h1>
   <span>
     your score is   {{ score }}/{{ questions.length }}
   </span>
 </section>
</main>
</template>

<style scoped>

.app{
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 100vh;
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
  color:rgb(239, 239, 69);
  font-size:1.25rem ;
}
.quiz-info .score{
  color: black;
  font-size: 1.25rem;
}
.option{
  display: block;
  padding: 1rem;
  background-color: rgb(67, 15, 89);
  color: aliceblue;
  margin-bottom: 0.5rem;
  border-radius: 0.5rem;
  cursor: pointer;
}
</style>
