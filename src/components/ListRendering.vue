<script setup>
import { ref } from "vue";

const items = ref([
  { id: 1, name: "사과", price: 1000 },
  { id: 2, name: "바나나", price: 2000 },
  { id: 3, name: "오렌지", price: 1500 },
]);

const newItem = ref({ name: "", price: 0 });

function addItem() {
  if (newItem.value.name && newItem.value.price) {
    items.value.push({
      id: items.value.length + 1,
      name: newItem.value.name,
      price: newItem.value.price,
    });
    newItem.value = { name: "", price: 0 };
  }
}
</script>

<template>
  <div class="demo-container">
    <h2>리스트 렌더링 (v-for)</h2>

    <div class="add-form">
      <input v-model="newItem.name" placeholder="상품명" />
      <input v-model.number="newItem.price" type="number" placeholder="가격" />
      <button @click="addItem">추가</button>
    </div>

    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>상품명</th>
          <th>가격</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.id">
          <td>{{ item.id }}</td>
          <td>{{ item.name }}</td>
          <td>{{ item.price }}원</td>
        </tr>
      </tbody>
    </table>
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

.add-form {
  margin-bottom: 20px;
}

input {
  margin: 5px;
  padding: 8px;
  border: 1px solid #3d3d3d;
  border-radius: 4px;
  background-color: #2d2d2d;
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

table {
  width: 100%;
  border-collapse: collapse;
}

th,
td {
  padding: 10px;
  border: 1px solid #3d3d3d;
  text-align: left;
  color: #ffffff;
}

th {
  background-color: #1a1a1a;
}
</style>
