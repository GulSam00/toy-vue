<script setup>
import { ref } from "vue";

const text = ref("");
const checkbox = ref(false);
const radio = ref("option1");
const select = ref("");
</script>

<template>
  <div class="demo-container">
    <h2>양방향 바인딩 (v-model)</h2>

    <div class="form-group">
      <label>텍스트 입력:</label>
      <input v-model="text" placeholder="입력하세요" />
      <p>입력된 값: {{ text }}</p>
    </div>

    <div class="form-group">
      <label>
        <input type="checkbox" v-model="checkbox" />
        체크박스
      </label>
      <p>체크 상태: {{ checkbox }}</p>
    </div>

    <div class="form-group">
      <label>
        <input type="radio" v-model="radio" value="option1" />
        옵션 1
      </label>
      <label>
        <input type="radio" v-model="radio" value="option2" />
        옵션 2
      </label>
      <p>선택된 옵션: {{ radio }}</p>
    </div>

    <div class="form-group">
      <label>선택 상자:</label>
      <select v-model="select">
        <option value="">선택하세요</option>
        <option value="option1">옵션 1</option>
        <option value="option2">옵션 2</option>
        <option value="option3">옵션 3</option>
      </select>
      <p>선택된 값: {{ select }}</p>
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

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 10px;
  color: #ffffff;
}

input[type="text"],
select {
  width: 100%;
  padding: 8px;
  margin: 5px 0;
  border: 1px solid #3d3d3d;
  border-radius: 4px;
  background-color: #2d2d2d;
  color: #ffffff;
}

input[type="checkbox"],
input[type="radio"] {
  margin-right: 5px;
}

p {
  margin-top: 5px;
  color: #cccccc;
}
</style>
