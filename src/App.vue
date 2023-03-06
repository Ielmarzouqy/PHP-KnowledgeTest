<!-- <script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style> -->
<script>
  // import {ref} from "vue";
  // const count = ref(0);
  // console.log(count);
  export default ({
    data(){
      return{
        count:0
      }
    },
    methods:{
      addCount(){
        // console.log("hiiiiiii");
        this.count = this.count +1
      }, 
      subtructCount(){
        this.count = this.count - 1
      }
    }

  })
</script>
<template>
  <div>
    <h4>
      counter is :
    </h4>
    <h1>{{count}}</h1>
    <button @click="subtructCount()">-</button>
    <button @click="addCount()">+</button>
  </div>
</template>
<style >
div{
  background-color: rgb(214, 186, 240);
}
</style>