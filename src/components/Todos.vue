<template> 
    <div>
        <h2>Todos List</h2>
        <div class="card" v-for="todo in todos" :key="todo.id" >
        <TodoItem :todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
        </div>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

export default {
name:'Todos',
  components: {
       TodoItem
 },
  
   props:['todos']
}
</script>
 
<style scoped>

</style>