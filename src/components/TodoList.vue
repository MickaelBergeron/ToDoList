<template>
    <AddTodo v-on:addTodo="addTodo"></AddTodo>
    <Todo v-for="todo in todos" 
        :key="todo.id" 
        :todo="todo" 
        v-on:deleteTodo="deleteTodo"></Todo>
</template>

<script>
import Todo from './Todo.vue';
import AddTodo from './AddTodo.vue';

export default {
    components: {
        Todo,
        AddTodo
    },
    data() {
      return { 
        todos: [{id:1, name:"eat"}, {id:2, name:"sleep"}, {id:3, name:"code"}]  
      }
    },
    methods: {
        deleteTodo(id) {
            for(let i=0; i<this.todos.length; i++) {
                if(this.todos[i].id == id) {
                    this.todos.splice(i,1);
                }
            }
        },
        addTodo(text) {
            let nextId = this.todos.length + 1;
            this.todos.push({id:nextId, name:text});
        }
    }
}
</script>

<style>

</style>