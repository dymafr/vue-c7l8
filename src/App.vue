<template>
  <h2>Form</h2>
  <input ref="input" type="text" placeholder="Nom" />
  <ul>
    <li ref="fruitRef" v-for="fruit of arr" :key="fruit">{{ fruit }}</li>
  </ul>
  <Blog ref="blogRef" />
</template>

<script setup lang="ts">
import { onMounted, reactive, ref } from 'vue';
import Blog from './Blog.vue';

const input = ref<HTMLInputElement | null>(null);
const arr = reactive(['pomme', 'fraise', 'poire']);
const fruitRef = ref<HTMLLinkElement[] | []>([]);
const blogRef = ref<InstanceType<typeof Blog> | null>(null);

onMounted(() => {
  console.log(input.value?.focus);
  console.log(fruitRef.value);
  console.log(blogRef.value?.count);
  console.log(blogRef.value?.arrTest);
  blogRef.value?.display();
});
</script>

<style scoped lang="scss"></style>
