<script setup>
import { ref } from "vue";

const isVisible = ref(true);
const showType = ref("v-if");
</script>

<template>
  <div class="demo-container">
    <h2>조건부 렌더링</h2>
    <div class="controls">
      <button @click="isVisible = !isVisible">토글</button>
      <select v-model="showType">
        <option value="v-if">v-if</option>
        <option value="v-show">v-show</option>
      </select>
    </div>

    <div v-if="showType === 'v-if'">
      <p v-if="isVisible">v-if로 보이는 텍스트</p>
      <p v-else>v-if로 숨겨진 텍스트</p>
    </div>

    <div v-else>
      <p v-show="isVisible">v-show로 보이는 텍스트</p>
      <p v-show="!isVisible">v-show로 숨겨진 텍스트</p>
    </div>
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

.controls {
  margin-bottom: 20px;
}

button,
select {
  margin: 5px;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  background-color: #2d2d2d;
  color: #ffffff;
}

button {
  background-color: #42b983;
  border: none;
}

button:hover {
  background-color: #3aa876;
}

select {
  border: 1px solid #3d3d3d;
}
</style>
