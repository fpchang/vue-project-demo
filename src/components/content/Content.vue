<template>
<div>
  <router-view></router-view>
</div>
   
</template>

<script>
import VueRouter from 'vue-router';
import Content1 from './Content1';
import Content2 from './Content2';
import Content3 from './Content3';
const routerObj=new VueRouter({
  routes:[
    {path:"/",component:Content1},
    {path:"/content1",component:Content1},
    {path:"/content2",component:Content2},
    {path:"/content3",component:Content3}
  ]
});
export default {
  name: 'Content',
  data () {
    return {
      msg: 'Welcome to content'
    }
  },
  methods:{
        
  },
   components:{
   "Content1":Content1,
   "Content2":Content2,
   "Content3":Content3
  },
  router:routerObj
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
