<template>
  <todoinput></todoinput>
  <todolist></todolist>
  <todofooter></todofooter>
</template>

<script>
import Todofooter from './components/todofooter.vue'
import todoinput from './components/todoinput.vue'
import Todolist from './components/todolist.vue'
export default {
  components: { todoinput, Todolist,Todofooter, },

}
</script>

<style>

</style>