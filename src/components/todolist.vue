<template>
  <ul>
    <li v-for="(item, i) in todoItem" :key="i" class="itemList">
      <div class="list">
        <i class="fa-regular fa-square-check"></i>
        {{ item }}
      </div>
      <div class="del" @click="removeDel(i,item)">
        <i class="fa-regular fa-trash-can"></i>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  props: ["todoItem"],
  methods:{
    removeDel(num,item){
      this.$emit("reDel",num,item)
    }
  }
};
</script>

<style lang="scss">
.itemList {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 35px;
  margin-bottom: 5px;
  .list {
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .del {
    height: 100%;
    background: #eee;
    padding: 0 20px;
    cursor: pointer;
    align-self: flex-start;
    display: flex; justify-content: center; align-items: center;
  }
}
</style>