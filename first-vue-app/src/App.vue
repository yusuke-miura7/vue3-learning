<!-- JavaScript部分 -->
<script setup>
console.log('Hello World');
let message = 'Hello world'
// const message = '<h2>Hello world</h2>'

const upperCase = () =>{
  message = message.toUpperCase();
};

upperCase();

</script>

<!-- html部分 -->
<template>
  <div>
    <h1>Vue 3 入門</h1>
    <p>{{ message }}</p>
    <div v-text="message"></div>
    <div v-html="message"></div>
    <!-- <h1> -->
  </div>
</template>

<!-- css部分 -->
<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
