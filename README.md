# vue-cli3练习项目

## 在views文件夹First.vue作为根页面

1. 完成基本html结构
2. 在router中设置根页面为First.vue
3. 完成基本css样式

## 左边商品列表

1. 新建Left.vue
2. 注册为First.vue的子组件

## 右边商品展示区域

1. 新建Right.vue
2. 注册为First.vue的子组件

## 功能:点击对应的商品列表,展示对应的商品区域

### 商品列表之间为兄弟关系,兄弟间传值要使用到事件总线

1. 新建VueEvent.js文件,写入代码`import Vue from 'vue';export default new Vue`
2. 在商品列表页面引入VueEvent.js,给每个商品列表注册相应的点击事件,在事件内部通过`VueEvent.$emit('val','1')`将数据传入
3. 在右边商品展示区域引入VueEvent.js,通过事件`VueEvent.$on('val',(m)=>{this.kk=m})`来获取商品列表页面传入的数据

## 读取json文件

1. 通过axios来请求json文件数据
2. 给Vue原型注册axios,让每个Vue实例对象都能使用这个方法 `Vue.prototype.$axios=axios`

## 对应的商品列表展示请求对应的json数据

1. 商品列表展示区与商品数据是父子关系,所以要利用父子间传值给商品列表传值
2. 通过父组件传过来的值来确定请求数据的url
3. 理由watch属性监听父组件传过来的值的变化来改变去重新请求数据