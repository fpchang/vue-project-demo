<template>
  <div class="con">
    <el-button type="text" @click="dialogVisible = true">点击打开 Dialog</el-button>
    <el-dialog title="提示" :visible.sync="dialogVisible" width="30%">
      <div>
        <selectData @callbackData="getSelectData" :params=sendValue></selectData>
      </div>
    </el-dialog>
    <div>{{getSelectValue}}</div>
  </div>
</template>

<script>
import selectData from '@/components/common/selectData'
export default {
  name: "Content1",
  data() {
    return {
      msg: "Welcome to content1",
       dialogVisible: false,
       sendValue:"request--888",
       getSelectValue:""
    };
  },
  components:{
    selectData:selectData
  },
  methods:{
    getSelectData(value){
      alert(value)
      this.dialogVisible=false;
    }
    
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
</style>
