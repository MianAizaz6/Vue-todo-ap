<template>
  <div id="app">
    <Todos v-bind:todos = "todos" v-on:del-todo="Delete"/>
  </div>
</template>

<script>

import Todos from './components/Todos.vue';

export default {
  name: 'App',
  components: {
    Todos
  },
  data(){
    return{
      todos:[
        {
          id:1,
          title:'Learning Vue Js',
          description:'The First task is to learn vue js to complete the project',
          completed:false,
        },
        {
          id:2,
          title:'Learn vuex',
          description:'Learn the Vuex to manage global store management',
          completed:false,
        },
        {
          id:3,
          title:'Learn structure Of the Vuex',
          description:'The basic thing is to understand the structure of the vuex so to use it in a good way.',
          completed:true,
        }
      ]
    }
  },
  methods:{

    Delete(id){
    this.todos = this.todos.filter(todo => todo.id !== id); 
}
  }
}
</script>

<style>
#app{
  padding: 50px;
  position: absolute;
  top:10px;
  left: 200px;

}

</style>
