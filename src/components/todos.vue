<template>
  <div class="todos">
    <div class="content">
        <input type="text" v-model="mylist"  @keyup.enter="login" placeholder="请输入今天的任务清单">
      </div>
  </div>
</template>

<script>
export default {
  name: 'todos',
  props: {
     
  },
  data(){
      return {
          mylist:""
      }
  },
  methods:{
      login(){
          
          if(this.mylist==""){
              window.confirm('不能为空!')
              return 
          }
          var obj = {}
          obj.things = this.mylist
          obj.hasfinished = false;
          this.$emit('add',obj)
      }
  }
}
</script>


<style scoped lang="less">
.content{
      input{
        display: inline-block;
        width:100%;
        padding-left:20px;
        box-sizing: border-box;
      }
    }
</style>
