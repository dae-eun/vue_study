<template>
  <!--html-->
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <!-- <button v-on:click="addTodo">add</button> -->
    <span class="addContainer">
      <i class="fa-solid fa-plus" v-on:click="addTodo"></i>
    </span>
  </div>
</template>

<script>
export default {
  //  js script
  data:function () {
    return{
      newTodoItem:"",
    }
  },
  methods:{
    addTodo:function(){
      if (this.newTodoItem!=='') {
        this.$emit('addTodoItem', this.newTodoItem);
        this.clearInput();
      }
    },
    clearInput:function(){
      this.newTodoItem='';
    }
  }
}
</script>

<style scoped>
  /* css */
  input:focus{
    outline: none;
  }
  .inputBox{
    background:#fff;
    height:50px;
    line-height: 50px;
    border-radius: 5px;
  }
  .inputBox input{
    border-style: none;
    font-size: 0.9rem;
  }
  .addContainer{
    float: right;
    background: linear-gradient(to right, #6478fb, #8763fb);
    display: block;
    width: 3rem;
    border-radius: 0 5px 5px 0;
  }
  .addBtn{
    color:#fff;
    vertical-align: middle;
  }
</style>