<script setup>
import { ref, computed, watch } from 'vue';

const searchText = ref('');
const liveText = ref('');
const waringMessage = computed(() => '10자를 초과했습니다!');
const isWaring = ref(false);

watch(searchText, () => {
  if (searchText.value.length > 10) {
    liveText.value = waringMessage.value;
    isWaring.value = true;
  } else {
    liveText.value = searchText.value;
    isWaring.value = false;
  }
});
</script>
<template>
  <div>
    <input type="text" v-model="searchText" />
    <h1 :class="{ 'red-text': isWaring }">{{ liveText }}</h1>
  </div>
</template>
<style>
.red-text {
  color: red;
}
</style>
