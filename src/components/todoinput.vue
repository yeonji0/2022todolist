<template>
  <div class="searchInput">
    <input
      type="text"
      class="inp"
      placeholder="오늘의 할일"
      v-model="newTodoItem"
    />
    <div class="btn" @click="todoItem">할일</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: "",
    };
  },
  methods: {
    todoItem(){
      let value = this.newTodoItem;
      this.$emit("addTodo", value);
    },
  },
};
</script>

<style lang="scss">
.searchInput {
  display: flex;
  gap: 5px;
  .inp {
    flex: 1 0 auto;
    text-indent: 10px;
  }
  .btn {
    line-height: 40px;
    padding: 0 10px;
    background: gray;
    color: white;
  }
}
</style>