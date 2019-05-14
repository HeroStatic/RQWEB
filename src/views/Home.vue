
<style lang="less" scoped>
 
  .center{
    width:400px;
    height: 400px;
    border:1px solid red;
    position: absolute;
    left:50%;
    top:50%;
    padding:10px;
    margin-left: -200px;
    margin-top:-200px;
    overflow: hidden;

  }

</style>

<template>
  <div class="home">

    <div class="center">
     <todos  @add="addTolist" />
     <tolist :todos="todos" @deletelist="deletTolist" />
     <footerlist/>
    </div>
  </div>
</template>

<script>
import todos from "../components/todos.vue"
import tolist from "../components/tolist.vue"
import footerlist from "../components/footerlist.vue"
export default {
  name: 'home',
  data() {
      return {
        // isCollapse: false
        todos:[
          {
             things:"打场高尔夫",hasfinished:true
          },
          {
             things:"会见奥巴马",hasfinished:false
          },
          {
             things:"回家写代码",hasfinished:false
          },
          {
             things:"回家吃饭",hasfinished:true
          }
        ]
      };
    },
    methods: {
      addTolist(todos){

         this.todos.unshift(todos)
      },
      deletTolist(index){
        console.log(index)
        this.todos.splice(index,1)
      }
    },
    components:{
      todos,
      tolist,
      footerlist
    }
}
</script>
<style>
 /* .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  

  
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  
  body > .el-container {
    margin-bottom: 40px;
  }
  

    .el-menu-vertical-demo:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
 
  } */

</style>
