<template>
    <header>
      <div class="pic">
        <Pictures
          v-for="picture in pictures"
          :key="picture.picId"
          :pic-id="picture.picId"
          :pic-src="picture.picSrc"
          :pic-alt="picture.picAlt"
          :pic-height="picture.picHeight"
          :pic-width="picture.picWidth"
        style="margin: 5px"/>
      </div>
    </header>
    <main>
    </main>
</template>

<script setup>
import Pictures from './pic/Pictures.vue';
import {onBeforeMount, onMounted, onUpdated, ref, watch} from "vue";

let pictures = ref([
  {
    picId: 1,
    picSrc: "/vertical.svg",
    picAlt: "vertical picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 2,
    picSrc: "/horizontal.svg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 3,
    picSrc: "/vertical.svg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 4,
    picSrc: "/horizontal.svg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 5,
    picSrc: "/pictures/panda1.jpg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 6,
    picSrc: "/pictures/panda2.jpeg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 7,
    picSrc: "/pictures/panda3.jpeg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },
  {
    picId: 8,
    picSrc: "/horizontal.svg",
    picAlt: "horizontal picture",
    picHeight: 20,
    picWidth: 20,
  },

  ])

const deviceWidth =  ref(document.body.clientWidth);

onBeforeMount(() => {
  pictures = changeStyle(pictures)
})

watch(() => deviceWidth.value, (newValue) => {
  console.log("deviceWidth", newValue)
})

function changeStyle(pictures) {
  // let deviceWidth =  document.body.clientWidth;
  console.log("deviceWidth", deviceWidth.value)
  let targetHeight = 250;
  if (deviceWidth < 640) {
    targetHeight = 170;
  } else if (deviceWidth < 960) {
    targetHeight = 210;
  }
  console.log("targetHeight", targetHeight)
  console.log(pictures.value)
  for(let i=0; i < pictures.value.length; i++) {
    // console.log(pictures.value[i])
    let imgObj = new Image()
    imgObj.src = pictures.value[i].picSrc
    console.log(imgObj)
    console.log(imgObj.height)
    console.log(imgObj.width)
    pictures.value[i].picWidth = imgObj.width * targetHeight / imgObj.height
    pictures.value[i].picHeight = targetHeight
    console.log(pictures.value[i].picHeight)
    console.log(pictures.value[i])
  }
  return pictures
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