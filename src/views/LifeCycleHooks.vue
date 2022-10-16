<script setup>
import { ref, onMounted, onUpdated, onUnmounted } from "vue";

const el = ref();
const buttonCountRef = ref();
const count = ref(1);
let intervalId;

onMounted(() => {
  el.value; // <div>
  intervalId = setInterval(() => {
    // ...
  });
  console.log("____onMounted____ template element --> ", el.value);
});
onUpdated(() => {
  console.log(
    "____onUpdated____ button text --> ",
    buttonCountRef.value.textContent
  );
});
onUnmounted(() => {
  clearInterval(intervalId);
  console.log("____onUnmounted____ About Page has been unmounted");
});
</script>
<template>
  <div ref="el">
    <h1>This is A Demo Page for Lifecycle Hooks Training</h1>
    <button ref="buttonCountRef" @click="count++">counter {{ count }}</button>
  </div>
</template>
