<template>
  <div class="clearAll" @click="$emit('clearAll')">
    clear All
  </div>
</template>

<script>
export default {

}
</script>

<style>
.clearAll{
    display: flex;justify-content: center;align-items: center;
    height: 50px; background: gray;color: #fff;
    border-radius: 10px;
}

</style>