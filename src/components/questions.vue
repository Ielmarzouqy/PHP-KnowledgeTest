<script>
</script>

<template>
    <div v-for="quiz in quizes" :key="quiz.id" class="containerD">
        <div  id="question-container" class="" >  
            <h1  class="infoTitle">Quiz PHP</h1>                    
            <div id="question">{{ quiz.questions.text }} </div>
            <div id="answers" class="btn-grid"></div>
              
        </div>
        <div class="">
            <button id="next"  class="next-btn btn hide">Next</button>
            <button id="result"  class="res-btn btn hide">Result</button>

        </div>
    </div>

</template>

<style scoped>
#question {
    justify-content: center;
    margin-left: 33%;
    width: 855px;
    max-width: 35%;
    background-color: #fffefe;
    border-radius: 5px;
    padding: 13px;
    box-shadow: 0 0 4px 1px;
    position: relative;
  }
  
  .btn-grid {
    display: grid;
    grid-template-columns: repeat(2, auto);
    gap: 10vh;
    margin: 10vh 21vh;
  }
  .btn-grid .btn {
    color: #f8fafa;
    border-radius: 5px;
    border-color: #E8A69A;
    padding: 13px;
    font-size: larger;
    cursor: pointer;
    background: rgba(58, 32, 80, 0.9490196078);
  }
  
  .btn.correct {
    background-color: #5cb85c;
  }
  
  .btn.wrong {
    background-color: rgb(210, 9, 9);
  }
  
  .next-btn {
    border: none;
    padding: 2px 15px;
    width: 130px;
    height: 60px;
    margin-left: 520px;
    font-size: 20px;
    cursor: pointer;
    color: aliceblue;
    background: #E8A69A;
    border-radius: 8px;
  }
  
  .res-btn {
    margin-left: 5px;
  }
</style>