<script setup>
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps({
  name: String,
});

const emits = defineEmits(['greet']);

function sendGreeting() {
  emits('greet', `Hello, ${props.name}!`);
}
</script>
<template>
  <div>
    <button @click="sendGreeting">Send Greeting</button>
  </div>
</template>
