<script setup>
import { ref } from 'vue'

const num = ref(1)
// console.log(num.value);
// setInterval(() => {
//     num.value++
// }, 500);
function clickme() {
  num.value++
}
</script>

<template>
  <div>
    {{ num }}

    <button type="button" v-on:click="clickme">點我</button>
  </div>
</template>
