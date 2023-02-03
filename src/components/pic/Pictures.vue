<template>
  <img :id="picId" :src="picSrc" :alt="picAlt"/>
</template>

<script setup>
import { ref } from 'vue';

const props = defineProps(['picId', 'picSrc', 'picAlt'])
const picId = ref(props.picId)
const picSrc = ref(props.picSrc)
const picAlt = ref(props.picAlt)
</script>