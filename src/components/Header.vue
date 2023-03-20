<script setup>
import { ref } from "vue";
import { useStore } from "../store/store";

const store = useStore();

const url = ref("");

function handleSubmit() {
  console.log(url);
  if (!!url.value) {
    store.registerNewSource(url.value);
  }
}
</script>

<template>
  <div class="header">
    <img alt="icon feedly" src="../assets/feedly-48.png" >
    <h1>Feedly</h1>
    <form @submit.prevent="handleSubmit">
      <input class="input" required type="url" v-model="url" />
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<style scoped>
.header {
  background: #14495E;
  grid-area: header;
  justify-self: stretch;

  display: flex;
  justify-content: center;

  padding: 10px;
}

form {
  width: 100%;
  display: flex;
  justify-content: center;
  gap: 5px;
}
.input {
  border: none;
  width: 400px;
}
button {
  border: none;
  background-color: #41B883;
  color: white;
  padding: 5px 10px;
}

h1{
  color: #41B883;
  font-weight: normal;
  font-size: 15px;
  font-family: Arial;
  padding-left: 7px;
}

img{
  padding-left: 6px;
  height: 30px;
}

</style>