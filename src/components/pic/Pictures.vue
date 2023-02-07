<template>
  <img :id="picId" :src="picSrc" :alt="picAlt" :width="picWidth" :height="picHeight"/>
</template>

<script setup>
import { ref } from 'vue';

const props = defineProps(['picId', 'picSrc', 'picAlt', 'picHeight', 'picWidth'])
const picId = ref(props.picId)
const picSrc = ref(props.picSrc)
const picAlt = ref(props.picAlt)
const picHeight = ref(props.picHeight)
const picWidth = ref(props.picWidth)
</script>