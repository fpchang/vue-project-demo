<template>
    <div class="home">
    <div class="container">
      <div class="logo"></div>
      <div class="content">
        <div class="leftmenu">
          <!-- @menuChange="menuChange 监控子组件像父组件发送数据  -->
          <LeftMenu @menuChange="menuChange" :msg="msg"></LeftMenu>
        </div>
        <div class="rightContent">
         <Content v-show="contentName=='content'"></Content>
         <chart v-show="contentName=='chart'"></chart>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueRouter from 'vue-router';
import LeftMenu from './LeftMenu.vue'
import Content from './content/Content.vue'
import chart from './chart.vue'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'home well',
      contentName:"content"
    }
  },
  components:{
    "LeftMenu":LeftMenu,
    "Content":Content,
    "chart":chart
  },
  methods:{
    menuChange(name){
      this.contentName=name;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{
  margin:0;
  padding:0;
}
.container .logo{
  background: gray;
  height: 3rem;
}
.content{
  display: flex;
}
.content .leftmenu{
  width: 15rem;
}
.content .rightContent{
  flex: 1;
}
</style>
