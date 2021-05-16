<template>
  <div id="app">
    <div class="box center">
      <span>刘高浔</span>
      <span>刘高墨</span>
    </div>
    <button @click="handleClick" class="btn1">选名</button>
    <button @click="handleCancel" class="btn2">清空</button>
    <div class="name-box">{{this.name}}</div>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      name1: "刘高浔",
      name2: "刘高墨"
    };
  },
  methods: {
    handleClick() {
      let random = Math.random() * 10 + 1;
      let num = Math.round(random);
      console.log(num);
      if (num > 5) {
        this.name = this.name1;
      } else {
        this.name = this.name2;
      }
    },
    handleCancel() {
      this.name = "";
    }
  }
};
</script>

<style lang="scss">
#app {
  background-color: #333;
  width: 100vw;
  height: 100vh;
  color: #fff;
  font-size: 50px;
  & .box {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }
}
.btn1,
.btn2 {
  width: 4rem;
  height: 2.5rem;
  font-size: 1rem;
  color: #ff0f00;
  background-color: #e3e4e5e6;
}
.name-box {
  margin: 0 auto;
  padding: 0.5rem;
  border-radius: 0.3rem;
  width: 5rem;
  text-align: center;
  margin-top: 50px;
  color: #ff0;
  background-color: #777;
}
</style>
