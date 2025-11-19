<script setup>
import Practice2Child_composition from './Practice2Child_composition.vue';
import { ref } from 'vue';

const childName = ref('Alice');

function handleGreeting(message) {
  console.log(message);
}
</script>
<template>
  <div>
    <Practice2Child_composition :name="childName" @greet="handleGreeting" />
  </div>
</template>
