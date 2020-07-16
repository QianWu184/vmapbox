<template>
  <div id = "messageCard">
      {{info.name}}
  </div>
</template>
<script>
export default {
  props:{
      info:{
        type: Object
      }
  },
  data(){
    return{
      
    }
  }
}
</script>
<style scoped>
    #messageCard{
      width: 100%;
      height: 100px;
      box-sizing: border-box;
      border:  1px solid rgba(0,0, 0, 0.2);
    }
</style>