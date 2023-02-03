<template>
  <div class="img-item" :style="{flexGrow: width,  width: width + 'px'}">
    <a href="#" :style="{paddingTop: paddingTop + '%'}">
      <img :data-src="{src}" :src="{src}" width="100%" height="100%" :alt="alt">
    </a>
  </div>
</template>

<script setup>
import {ref} from "vue";

defineProps({
  width: Number,
  paddingTop: Number,
  src: String,
  alt: String,
})
// const width = ref('30');
export default {
  name: "testHeaderPic"
}
</script>



<style scoped>

</style>