<template>
  <div class="footerlist">
    <input type="checkbox" v-model="isChcek">
    已完成{{hasfinishCount}}件/总计{{todos.length}}件
    <button @click="handleClick">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: "footerlist",
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  methods: {
    handleClick() {
      this.$emit("deleisdo");
    }
  },
  computed: {
    hasfinishCount() {
      return this.todos.reduce((prev, cur) => {
        return prev + (cur.hasfinished ? 1 : 0);
      }, 0);
    },
    isChcek: {
      get() {
        return this.hasfinishCount === this.todos.length&&this.todos.length>0;
      },
      set(value) {
        this.$emit("queryall", value);
      }
    }
  }
};
</script>


<style scoped lang="less">
.footer {
  margin-top: 40px;
}
</style>
