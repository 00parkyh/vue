<script setup>
import { computed, reactive } from 'vue';

const cart = reactive({
  item1: { name: '아이폰17 pro', price: 10000, count: 10 },
  item2: { name: '에어팟 프로 2세데', price: 3500, count: 20 },
});
const totalPrice = computed(() => {
  return (
    cart.item1.price * cart.item1.count + cart.item2.price * cart.item2.count
  );
});
</script>
<template>
  <div>
    <h1>장바구니</h1>
    <ul>
      <li v-for="item in cart">
        {{ item.name }} : {{ item.price }}원, {{ item.count }}개
      </li>
    </ul>
    <br />
    <h2>총 금액 : {{ totalPrice }}원</h2>
  </div>
</template>
