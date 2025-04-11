<script setup>
import { ref } from "vue";

const count = ref(0);
const message = ref("반응형 데이터입니다!");
</script>

<template>
  <div class="demo-container">
    <h2>반응형 데이터 (Reactivity)</h2>
    <p>{{ message }}</p>
    <p>카운트: {{ count }}</p>
    <button @click="count++">증가</button>
    <button @click="count--">감소</button>
  </div>
</template>

<style scoped>
.demo-container {
  padding: 20px;
  border: 1px solid #3d3d3d;
  border-radius: 8px;
  margin: 10px;
  color: #ffffff;
}

button {
  margin: 5px;
  padding: 8px 16px;
  background-color: #42b983;
  color: #ffffff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

button:hover {
  background-color: #3aa876;
}
</style>
