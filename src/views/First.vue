<template>
  <div class="main">
    <div class="left">
        <Left></Left>
    </div>
    <div class="right">
      <div class="top">
        <img src="img/title.jpg" alt />
      </div>
      <div class="bottom">
          <Right></Right>
      </div>
    </div>
  </div>
</template>

<script>
import Left from "../components/Left";
import Right from "../components/Right";
export default {
  components: {
      Left,
      Right
  }
};
</script>

<style lang="less">
* {
  margin: 0;
  padding: 0;
}
.main {
  width: 1200px;
  margin: 20px auto;
  .left {
    width: 100px;
    float: left;
    margin-left: 10px;
    background-color: #f5f5f5;
    height: 500px;
  }
  .right {
    width: 1000px;
    float: left;
    margin-left: 10px;
    background-color: #f5f5f5;
    height: 500px;
    .top img {
      height: 200px;
      width: 1000px;
    }
  }
}
</style>