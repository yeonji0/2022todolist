<template>
  <div class="header">
    <h1>TODO LIST</h1>
  </div>
  <todo-input @addTodo="addTodoItem"></todo-input>
  <todo-list :todoItem="todoItem" @reDel="removeDel"></todo-list>
  <todo-footer @clearAll="clearAll"></todo-footer>
</template>

<script>
import TodoFooter from './components/todofooter.vue'
import TodoInput from './components/todoinput.vue'
import TodoList from './components/todolist.vue'
export default {
  components: { TodoInput, TodoList, TodoFooter },
  data(){
    return {
      todoItem:[]
    }
  },
  created(){
    for(let i=0;i<localStorage.length;i++){
      this.todoItem.push(localStorage.key(i))
    }
  },
  methods:{
    addTodoItem(item){
      console.log("할일추가" + item);
      this.todoItem.push(item);
       localStorage.setItem(item,item)
    },
    removeDel(num,item){
      console.log(num+"ok")
      this.todoItem.splice(num,1)
      localStorage.removeItem(item)
    },
    clearAll(){
      localStorage.clear();
      this.todoItem=[];
    }
  }

}
</script>

<style>
@import url('./assets/reset.css');
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
body{
  font-family: 'Roboto', sans-serif;
}

#app{
  width: 400px;
  margin: 0 auto;
}

</style>