<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>传递过来的值是 {{params}}</div>
    <div><el-button type="primary" v-on:click="confirm()">发送回数据</el-button></div>

  </div>
</template>

<script>
export default {
  name: 'selectData',
  data () {
    return {
      msg: 'select data'
    }
  },
   props:{params:{type:String,default:'mmmooo'}},
  //props:['params'],
  methods:{
    confirm(){
      this.$emit("callbackData", "这是传递过去的值==response 999");
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
