<script setup>

import HelloWorld from './components/HelloWorld.vue'
import TheHeaderVue from './components/TheHeader.vue';
import {onMounted} from "vue";

onMounted(() => {
  // clickButton()
})

function clickButton() {
  console.log(window.screen.width)
  console.log(window.screen.availWidth)
  console.log(document.body.clientWidth)

  console.log("111111111111")
}

</script>

<template>
  <div class="img-items">
    <TheHeaderVue/>
  </div>

  <div>
    <button :onclick="clickButton">This is a button</button>
  </div>

  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.img-items{
  display: flex;
  flex-wrap: wrap;
  overflow: hidden;
  background-color: aqua;
}

/*.img-item {*/
/*  margin-right: 10px;*/
/*  margin-bottom: 10px;*/
/*  background-color: #fff;*/
/*  box-shadow: 0 0 10px #ddd;*/
/*}*/



</style>
