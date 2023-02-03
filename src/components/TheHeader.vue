<template>
    <header>
      <div class="pic">
<!--        <Pictures-->
<!--          v-for="picture in pictures"-->
<!--          :key="picture.picId"-->
<!--          :pic-id="picture.picId"-->
<!--          :pic-src="picture.picSrc"-->
<!--          :pic-alt="picture.picAlt"-->
<!--          :style="{height: '20%', width: '20%'}"/>-->
      </div>
    </header>
    <main>
    </main>
</template>

<script setup>
import Pictures from './pic/Pictures.vue';
import {ref} from "vue";

const pictures = ref([
  {
    picId: 1,
    picSrc: "/vertical.svg",
    picAlt: "vertical picture",
  },
  {
    picId: 2,
    picSrc: "/horizontal.svg",
    picAlt: "horizontal picture",
  },
  {
    picId: 3,
    picSrc: "/vertical.svg",
    picAlt: "horizontal picture",
  },
  {
    picId: 4,
    picSrc: "/horizontal.svg",
    picAlt: "horizontal picture",
  }
  ])

function changeStyle(pictures) {
  let deviceWidth =  document.body.clientWidth;
  let targetWidth = 250;
  if (deviceWidth < 640) {
    targetWidth = 170;
  } else if (deviceWidth < 960) {
    targetWidth = 210;
  }
  for(let i=0; i < pictures.value.length; i++) {
    pictures
  }

}

</script>

<style scoped>
/*.pic{*/
/*  display: flex;*/
/*  !* padding: 10px;*/
/*  margin: 10px; *!*/
/*  !* vertical-align: top; *!*/
/*  !*max-width: 1920px;*!*/
/*  max-width: max-content;*/
/*  !* max-height: 1080px; *!*/
/*  !* width: 1920px; *!*/
/*  flex-direction: row;*/
/*  flex-wrap: wrap;*/
/*  justify-content: space-between;*/
/*  align-items: flex-start;*/


/*}*/

/*.pic_horizontal{*/
/*  !* background-color: blue; *!*/
/*  height: 15%;*/
/*  width: 15%;*/
/*  padding: 5px;*/
/*  flex-grow: 1;*/
/*  !* float: left; *!*/
/*}*/
/*.pic_vertical{*/
/*  !* background-color: blue; *!*/
/*  height: 15%;*/
/*  width: 15%;*/
/*  padding: 5px;*/
/*  flex-grow: 1;*/
/*  !* float: left; *!*/
/*}*/


</style>