<template>
  <div class="info-page hide " id="info-page">
    <div class="content">
        <div>
            <h1 id="info-title" class="info-title">Quiz PHP!</h1>
            <p id="content" >The test contains 10 questions and there is no time limit.<br>
                The test is not official, <br> 
                it's just a nice way to see how much you know, or don't know, about PHP. </p>
            <button id="start"  class="start-btn ">Start Quiz </button>
        </div>
        <div id="image">
            <img class="img-info" src="./assets/PHP6.png" alt="image">
        </div>
    </div>
   

</div>
</template>

<style scoped>

.info-page {
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: 100%;
  min-height: 600px;
  -webkit-animation: transitionIn-Y-bottom 0.5s;
          animation: transitionIn-Y-bottom 0.5s;
}
.info-page .content {
  display: flex;
  top: 100px;
}
.info-page .content p {
  border-color: #E8A69A;
  box-sizing: border-box;
  color: #f8fafa;
  margin-left: 58px;
  font-size: 19px;
  padding: 33px;
}
.info-page .content .info-title {
  top: 300px;
  left: 100px;
  color: #C01EA0;
  justify-content: center;
  align-items: center;
  margin-left: 100px;
}
.info-page .img-info {
  width: 100%;
  height: 100%;
  margin-top: 40px;
  margin-left: 50px;
}
.start-btn, .res-btn {
  border: none;
  padding: 2px 15px;
  width: 130px;
  height: 60px;
  margin-left: 80px;
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
