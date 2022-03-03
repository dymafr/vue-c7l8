<template>
  <button @click="toggle = !toggle">Toggle</button>
  <Blog
    v-if="toggle"
    v-for="title of titles"
    :title="title"
    :key="title"
    class="parent"
  />
</template>

<script setup lang="ts">
import { onMounted, reactive, ref } from 'vue';
import Blog from './Blog.vue';

const titles = ref(['Un titre', 'Un autre titre']);

const toggle = ref(true);
</script>

<style scoped lang="scss"></style>
