<template>
    <div class="zuhezhentingqi">
      <h3>组合式---watch侦听</h3>
      <p>{{ count }}</p>
      <button @click="addCount">增加</button>
      <hr>
    </div>
  </template>
  
  <script setup>
  import {ref,watch} from 'vue'
  import { watchCount } from '../utils/watchUtils';
  
  const count = ref(0);
  
  const addCount = (e) => {
    console.log(e, '888888888888');
    count.value++;
  };
  
  watchCount(count);
  </script>
  
  <style scoped>
  .zuhezhentingqi {
    color: green;
  }
  </style>