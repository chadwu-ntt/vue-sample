<template>
  <!-- id="app"，必須依賴 main.js $mount("#app") 裡面的名字(大小寫不同) -->
  <div id="app">
    <!-- {{ }}是用來表示「綁定資料」，裡面就是剛剛我為資料取的名字 -->
    <h1>{{test_title}}</h1>

    <!-- v-model，可以對input、textarea、select、checkbox等…這些輸入表單做雙向綁定，運做原理是透過監聽使用者輸入的事件來更新內容 -->
    <!-- 加入.lazy => 離開<input>時才更新 -->
    <!-- 加入.trim => 自動去掉空白 -->
    <input type="text" v-model.lazy.trim="myInputName" value="myInputName" />
    <p>大家好！我叫 {{ myInputName }}</p>
  </div>
</template>

<script>
export default {
  name: "test-1",
  //放資料的function
  data() {
    //回傳的內容
    return {
      test_title: "vue 第一次測試", //資料名字
      myInputName: "請輸入姓名"
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
