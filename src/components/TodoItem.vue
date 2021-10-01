<template>
    <div>
       
        <button @click="$emit('del-todo', todo.id)" class="check">X</button>
        <h3> {{todo.title}} </h3>
        <h5>{{ todo.description}} </h5>
        <button v-if="todo.completed" v-bind:class="{'iscomplete':todo.completed}" v-on:click="Complete"> Already Completed </button>
        <button v-else class="todo-btn" v-on:click="Complete"> Mark As Complete </button>
    
    </div>
</template>

<script>

export default {
   name:'TodoItem',
   props:["todo"],
   methods:{
       Complete(){
           this.todo.completed = !this.todo.completed;
       }
   }
}
</script>

<style>
    .card{
  background-color: antiquewhite;
  width: 500px;
  height: 140px;
  box-shadow: 2px 3px 4px grey;
  border-radius: 10px;
  padding: 10px 20px;
  margin-top: 20px;
}
.iscomplete{
     background-color: rgb(205, 94, 50);
    color: white;
    padding: 10px 20px;
    border: none;
    font-weight: 800;
}
.todo-btn{
    background-color: yellowgreen;
    color: white;
    padding: 10px 20px;
    border: none;
    font-weight: 800;
}
.check{
    float: right;
    border-radius: 50px;
    border: none;
    height: 25px;
    width: 25px;
    background-color: brown;
    color: white;
}
.check:hover{
    height: 30px;
    width: 30px;
    cursor: pointer;
}
</style>