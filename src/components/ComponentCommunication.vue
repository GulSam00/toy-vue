<script setup>
import { ref } from "vue";
import ChildComponent from "./ChildComponent.vue";

const parentMessage = ref("부모 컴포넌트의 메시지");
const childMessage = ref("");

function handleChildMessage(message) {
  childMessage.value = message;
}
</script>

<template>
  <div class="demo-container">
    <h2>컴포넌트 통신</h2>

    <div class="parent-section">
      <h3>부모 컴포넌트</h3>
      <p>자식으로부터 받은 메시지: {{ childMessage }}</p>
    </div>

    <ChildComponent
      :message="parentMessage"
      @message-from-child="handleChildMessage"
    />
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

.parent-section {
  margin-bottom: 20px;
  padding: 15px;
  background-color: #1a1a1a;
  border-radius: 4px;
}

h3 {
  margin-top: 0;
  color: #42b983;
}
</style>
