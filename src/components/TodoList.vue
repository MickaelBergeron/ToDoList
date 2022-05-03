<template>
  <Todo v-for="todo in todos" :key="todo.id" :todo="todo"></Todo>
</template>

<script>
import Todo from './Todo.vue';

export default {
    components: {
        Todo
    },
    data() {
      return { 
        todos: [{id:1, name:"eat"}, {id:2, name:"sleep"}, {id:3, name:"code"}]  
      }
    },
}
</script>

<style>

</style>