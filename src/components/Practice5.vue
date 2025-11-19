<script setup>
import { ref } from 'vue';
const inputRef = ref(null);
const inputValue = ref('');

function focusHandler() {
  if (inputRef.value) {
    inputRef.value.focus();
  }
  if (inputValue.value.length > 0) {
    alert(`${inputValue.value}`);
  }
}
</script>
<template>
  <div>
    <input type="text" v-model="inputValue" ref="inputRef" />
    <button @click="focusHandler">버튼</button>
  </div>
</template>
