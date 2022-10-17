<template>
  {{todoItem}}
  <ul>
    <li v-for="(item,i) in todoItem" :key="i">
      {{item}}
      </li>
  </ul>
</template>

<script>
export default {
  props:["todoItem"]

}
</script>

<style>

</style>