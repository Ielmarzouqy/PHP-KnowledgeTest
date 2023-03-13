<script>

</script>

<template>
    <div class="status hide" id="status-score">
        <div class="circular-progress hide">
          <div class="value-container hide">0%</div>
        </div>
      </div> 
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
  height: 100vh;
  background: linear-gradient(to right, #430D7D 18%, #471a3e 100%);
}

.status {
  height: 400px;
  width: 400px;
  background-color: #ffffff;
  position: absolute;
  transform: translate(-50%, -50%);
  top: 50%;
  left: 50%;
  border-radius: 8px;
  display: grid;
  place-items: center;
}

.circular-progress {
  position: relative;
  height: 250px;
  width: 250px;
  background-color: rgb(207, 38, 156);
  box-shadow: 20px 20px 40px rgba(60, 60, 150, 0.25);
  border-radius: 50%;
  display: grid;
  place-items: center;
}
.circular-progress::before {
  content: "";
  position: absolute;
  height: 84%;
  width: 84%;
  background-color: #ffffff;
  border-radius: 50%;
}
</style>