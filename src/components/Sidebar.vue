<script setup>
import { useStore } from "../store/store";

const store = useStore();

function handleClick(source) {
  const item = store.sources.find((i) => i === source);

  store.loadSource(item);
}
</script>

<template>
  <div class="sidebar">
    <div v-for="(source, index) in store.sources" :key="index">
      <a href="#" @click="() => handleClick(source)">{{ source.name }}</a>
    </div>
  </div>
</template>

<style scoped>
.sidebar {
  grid-column-start: 1;
  grid-column-end: 2;
  background-color: #34495E;
}

.sidebar a {
  color: #41B883;
  display: block;
  padding: 5px;
  text-decoration: none;
}

.sidebar a:hover {
  background-color: rgb(0, 0, 0);
}
</style>