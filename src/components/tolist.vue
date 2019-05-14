<template>
  <div class="tolist">
    <div class="list">
        <ul>
          <!-- <li>
              <input type="checkbox"> 打场高尔夫<button>删除</button>
          </li> -->
         <todoitem @deleter="handledelete"  v-for="(item,index) in todos" :key="index" :todo="item"  :index="index"/>
        </ul>
      </div>
  </div>
</template>

<script>
import todoitem from "../components/todoitem"
export default {
  name: 'tolist',
  props: ['todos'],
  components:{
      todoitem
  },
  methods:{
   handledelete(index){
     this.$emit('deletelist',index)
   }
  }
}
</script>


<style scoped lang="less">

    .list{
      ul{
        list-style: none;
        margin-top:20px;
      
      }
    }
</style>
