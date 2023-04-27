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

const isActive = true;
const isBlack = true;

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
    <!-- v-bindの確認 -->
    <p class="active">v-bindの設定方法の確認</p>
    <!-- 動的なクラス適用 -->
    <p class="{active: isActive }">v-bindの設定方法の確認</p>
    <!-- 複数クラスの適用 -->
    <p class="underLine" :class="{active:isActive, back:isBlack}">
    v-bindの設定方法の確認
    </p>
  </div>
  </div>
</template>

<!-- css部分 -->
<style scoped>
.active {
  color: red;
  font-weight: 900;
}

.underLine{
  text-decoration: underline;
}
.back{
  background-color: black;
}
</style>
