<script setup>
import { ref } from "vue";
import ReactivityDemo from "./components/ReactivityDemo.vue";
import ConditionalRendering from "./components/ConditionalRendering.vue";
import ListRendering from "./components/ListRendering.vue";
import TwoWayBinding from "./components/TwoWayBinding.vue";
import ComponentCommunication from "./components/ComponentCommunication.vue";

const tabs = [
  { id: "reactivity", name: "반응형 데이터", component: ReactivityDemo },
  { id: "conditional", name: "조건부 렌더링", component: ConditionalRendering },
  { id: "list", name: "리스트 렌더링", component: ListRendering },
  { id: "binding", name: "양방향 바인딩", component: TwoWayBinding },
  {
    id: "communication",
    name: "컴포넌트 통신",
    component: ComponentCommunication,
  },
];

const activeTab = ref("reactivity");
</script>

<template>
  <div class="app">
    <header>
      <h1>Vue.js 주요 기능 데모</h1>
    </header>

    <nav class="tabs">
      <button
        v-for="tab in tabs"
        :key="tab.id"
        :class="{ active: activeTab === tab.id }"
        @click="activeTab = tab.id"
      >
        {{ tab.name }}
      </button>
    </nav>

    <main>
      <component :is="tabs.find((tab) => tab.id === activeTab).component" />
    </main>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  background-color: #1a1a1a;
  color: #ffffff;
}

.app {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

header {
  text-align: center;
  margin-bottom: 30px;
}

h1 {
  color: #42b983;
}

.tabs {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
  overflow-x: auto;
  padding-bottom: 10px;
}

.tabs button {
  padding: 10px 20px;
  background-color: #2d2d2d;
  border: 1px solid #3d3d3d;
  border-radius: 4px;
  cursor: pointer;
  white-space: nowrap;
  transition: all 0.3s ease;
  color: #ffffff;
}

.tabs button:hover {
  background-color: #3d3d3d;
}

.tabs button.active {
  background-color: #42b983;
  color: #ffffff;
  border-color: #42b983;
}

main {
  background-color: #2d2d2d;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}
</style>
