<template>
  <div class="header">
    <h1>TODO LIST</h1>
  </div>
  <todoinput @addTodo="addTodoItem"></todoinput>
  <todolist :todoItem="todoItem"></todolist>
  <todofooter></todofooter>
  {{todoItem}}
</template>

<script>
import Todofooter from './components/todofooter.vue'
import todoinput from './components/todoinput.vue'
import Todolist from './components/todolist.vue'

export default {
  components: { todoinput, Todolist,Todofooter, },
  data(){
    return{
      todoItem:[]
    }
  },
  methods:{
    addTodoItem(item){
      console.log(item);
      this.todoItem.push(item)
    }
  }

}
</script>

<style lang="scss">
@import url('./assets/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

#app{
  width: 400px;margin: 0 auto;
  }
</style>