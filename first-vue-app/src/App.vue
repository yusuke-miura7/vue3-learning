<!-- JavaScript部分 -->
<script setup>
console.log('Hello World');
let message = 'Hello world'
// const message = '<h2>Hello world</h2>'

const upperCase = () =>{
  message = message.toUpperCase();
};

upperCase();

const link = 'https://google.com';

</script>

<!-- html部分 -->
<template>
  <div>
    <h1>Vue 3 入門</h1>
    <p>{{ message }}</p>
    <div v-text="message"></div>
    <div v-html="message"></div>
  <div>
    <a v-bind:href="link">google</a>
    <p class="active">v-bindの設定方法の確認</p>
  </div>
  </div>
</template>

<!-- css部分 -->
<style scoped>
.active {
  color: red;
  font-weight: 900;
}
</style>
