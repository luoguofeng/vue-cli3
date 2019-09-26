<template>
  <div name="show">
    <ul class="goodList">
      <li v-for="(item, index) in list" :key="index">
        <img :src="item.img" alt />
        <p>{{item.goodName}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "show",
  data() {
    return {
      list: []
    };
  },
  created() {
    this.getData();
  },
  props: ["goodId"],
  methods: {
    //获取数据的方法
    getData() {
      let url = "";
      if (this.goodId == 1) {
        url = "json/bijiben.json";
      } else if (this.goodId == 2) {
        url = "json/shouji.json";
      } else {
        url = "json/bijiben.json";
      }
      this.$axios.get(url).then(res => {
        this.list = res.data;
      });
    }
  },
  watch: {
    goodId() {
      this.getData();
    }
  }
};
</script>

<style>
.goodList li {
  width: 200px;
  height: 200px;
  float: left;
  font-size: 9px;
  color: red;
  margin-bottom: 30px;
}
.goodList img {
  width: 180px;
  height: 180px;
}
</style>