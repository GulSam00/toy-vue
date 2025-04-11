<script setup>
import { ref } from "vue";

const props = defineProps({
  message: String,
});

const emit = defineEmits(["message-from-child"]);
const childInput = ref("");

function sendMessage() {
  emit("message-from-child", childInput.value);
  childInput.value = "";
}
</script>

<template>
  <div class="child-section">
    <h3>자식 컴포넌트</h3>
    <p>부모로부터 받은 메시지: {{ message }}</p>

    <div class="input-group">
      <input
        v-model="childInput"
        placeholder="부모에게 보낼 메시지"
        @keyup.enter="sendMessage"
      />
      <button @click="sendMessage">전송</button>
    </div>
  </div>
</template>

<style scoped>
.child-section {
  padding: 15px;
  background-color: #1a1a1a;
  border-radius: 4px;
  color: #ffffff;
}

.input-group {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}

input {
  flex: 1;
  padding: 8px;
  border: 1px solid #3d3d3d;
  border-radius: 4px;
  background-color: #2d2d2d;
  color: #ffffff;
}

button {
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
