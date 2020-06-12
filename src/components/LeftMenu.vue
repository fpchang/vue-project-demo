<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
      <ul>
        <li v-for="(value) in menuArray" v-on:click="getPage(value)" :key="value">{{value}}</li>
      </ul>

  </div>
</template>

<script>
import Vue from 'vue'
var vm = new Vue();//定义一个空的Vue实例
export default {
  name: 'LeftMenu',
  data () {
    return {
      msg: 'menu',
      menuArray:["content","chart"]
    }
  },
  methods:{
getPage(name){
   //   alert(name)
    /*  switch(name){
        case "content1":
          this.router.push("/content1")
          break;
          case "content2":
          this.router.push("/content2")
          break;
          case "content3":
          this.router.push("/content3")
          break;
      }
      */
     this.$emit("menuChange",name)
    }
  }
}

</script>
<style scoped>

</style>
