<script setup>
import { ref } from 'vue';

const emit = defineEmits(['formSubmit'])
const searchInput = ref('')

function handleSubmit(ev) {
  ev.preventDefault()
  emit('formSubmit', searchInput.value)
}
</script>

<template>
  <form @submit="handleSubmit">
    <input type="text" v-model="searchInput"> 
    <button>Show User</button> 
  </form>
</template>

<style scoped>
input,
button {
  max-width: 20rem;
  padding: .5rem;
}
input {
  background-color: #2A3642;
  border: 1px solid #42B883;
  border-radius: .25rem;
  color: #e5e5e5;
  margin: 1rem 1rem 1rem 0;
}
button {
  background-color: #42B883;
  border: unset;
  border-radius: .25rem;
  color: #2A3642;
  font-size: 1rem;
  font-weight: 700;
  text-transform: uppercase;
}
button:hover {
  cursor: pointer;
  filter: brightness(0.95);
}
</style>