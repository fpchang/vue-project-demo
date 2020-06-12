<template>
  <div class="left-menu">
    <!--
      
    <h1>{{ msg }}</h1>
      <ul>
        <li v-for="(value) in menuArray" v-on:click="getPage(value)" :key="value">{{value}}</li>
      </ul>
    -->
    <el-col :span="24">
      <el-menu
        default-active="2"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
      >
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-location"></i>
            <span>导航一</span>
          </template>
          <el-menu-item-group>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
          </el-menu-item-group>
        </el-submenu>
        <el-menu-item index="2">
          <i class="el-icon-menu"></i>
          <span slot="title">导航二</span>
        </el-menu-item>
        <el-menu-item index="3" disabled>
          <i class="el-icon-document"></i>
          <span slot="title">导航三</span>
        </el-menu-item>
        <el-menu-item index="4">
          <i class="el-icon-setting"></i>
          <span slot="title">导航四</span>
        </el-menu-item>
      </el-menu>
    </el-col>
  </div>
</template>

<script>
import Vue from "vue";
var vm = new Vue(); //定义一个空的Vue实例
export default {
  name: "LeftMenu",
  data() {
    return {
      msg: "menu",
      menuArray: ["content", "chart"]
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    getPage(name) {
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
      this.$emit("menuChange", name);
    }
  }
};
</script>
<style scoped>
.left-menu {
  margin: 0;
}
</style>
