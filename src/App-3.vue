<template>
  <!-- id="app"，必須依賴 main.js $mount("#app") 裡面的名字(大小寫不同) -->
  <div id="app">
    <select v-model="mySelectName">
      <option v-for="(item, index) in myArray" :key="index">{{ item }}</option>
    </select>
    <p>我的名子叫：{{ mySelectName }}</p>

    <!-- v-bind => 屬性綁定：「屬性 key 要帶入資料 index」 -->
    <ul v-for="(item, index) in myArray" v-bind:key="index">
      <li>{{ index }} - {{ item }}</li>
    </ul>
    <ul v-for="(item, index) in myArray2" v-bind:key="index">
      <li>
        {{ item.name }}
        <br />
        {{ item.mail }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "test-1",
  //放資料的function
  data() {
    //回傳的內容
    return {
      mySelectName: "請選擇姓名2",
      myArray: ["Adam", "Jack", "Candy", "Louis", "Lurry"],
      myArray2: [
        {
          name: "Adam",
          mail: "adam@xxx.com"
        },
        {
          name: "Jack",
          mail: "jack@xxx.com"
        },
        {
          name: "Candy",
          mail: "candy@xxx.com"
        },
        {
          name: "Louis",
          mail: "loui@xxx.com"
        },
        {
          name: "Lurry",
          mail: "lurry@xxx.com"
        }
      ]
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
