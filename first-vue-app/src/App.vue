<!-- JavaScript部分 -->
<script setup>
import { ref } from 'vue';
import { reactive} from 'vue';

// 双方向バイディング一つ目の書き方
const message = ref('Hello world');

const clickButton = () =>{
  console.log(message.value);
};

// 双方向バイディング二つ目の書き方
const form = reactive({
  message: 'Hello World',
});

const clickButton2 = () =>{
  console.log(form.message);
};

const link = 'https://google.com';

const isActive = true;
const isBlack = true;

//Reactivaityを持たせる
const stock = ref(5);
const increment=() =>{
  console.log(stock);
  stock.value+=1;
}

const clickdButton = () =>{
  console.log("ダブルクリックされました");
}

const clickColor = (event) =>{
  event.target.style.backgroundColor = 'red';
}

const send = () =>{
  console.log('send');
}

const users = [
  { id: 1, name: 'John Doe', email: 'john@test.com', admin: true },
  { id: 2, name: 'Jane Doe', email: 'jane@example.com', admin: false },
  { id: 3, name: 'Kevin MacDonald', email: 'kevin@test.com', admin: false },
];

</script>

<!-- html部分 -->
<template>
  <div>
    <h1>Vue 3 入門</h1>
    <p>{{ message }}</p>
    <div v-text="message">
    </div>
    <div v-html="message">
    </div>
  
    <a v-bind:href="link">google</a>
    <!-- v-bindの確認 -->
    <p class="active">v-bindの設定方法の確認</p>
    <!-- 動的なクラス適用 -->
    <p :class="{active: isActive }">v-bindの設定方法の確認2</p>
    <!-- 複数クラスの適用 -->
    <p class="underLine" :class="{active:isActive, back:isBlack}">
    v-bindの設定方法の確認
    </p>

    <!-- v-ifの確認 -->
    <div v-if="stock >5">まだ商品に在庫数に余裕があります</div>
    <div v-else-if="stock === 0">申し訳ありません。現在売り切れです。</div>
    <div v-else>在庫数が少なくなっております。お急ぎください</div>

    <!-- v-forの確認 -->
    <div>
    <p v-for="user in users" :key="user.id">{{ user.id }}:{{ user.name }}({{ user.email }})</p>
    <p v-for="(user, index) in users" :key="user">
    {{ index }}-{{ user.id }}{{ user.name }}{{ user.email }}</p>
    <div v-for="user in users" :key="user.id">
      <div v-if="!user.admin">
        {{ user.name }}
      </div>
    </div>
    </div>
    
    <!-- v-on:clickの確認 -->
    <button @click="increment">在庫を増やす</button>
    <button @dblclick="clickdButton">ダブルクリック</button>
    <button @click="clickColor">赤色に変更</button>

    <!-- ページのリロードを防ぐ -->
    <form @submit.prevent="send">
      <!-- <button>送信</button> -->
      <button @keyup.right="send">rightで送信</button>
    </form>

    <!-- v-modelで双方向バイディング(reactivity持たせる必要あり) -->
    <p>{{ message }}</p>
    <input v-model="message" />
    <button @click="clickButton">Click</button>

    <p>{{ form.message }}</p>
    <input v-model="form.message" />
    <button @click="clickButton2">Click2</button>
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
