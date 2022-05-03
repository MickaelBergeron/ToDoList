<template>
    <div class="todobox">
        <span>{{todo.name}}</span>
        <button id="btnDelete" @click="deleteTodo(todo.id)">X</button>
    </div>
</template>

<script>
export default {
    props: ['todo'],
    methods: {
        deleteTodo(id) {
            this.$emit('deleteTodo', id);
        }
    }
}
</script>

<style>
    .todobox {
        width: 50%;
        border: 1px solid black;
        text-align: center;
        margin: auto;
        margin-bottom: 5px;
        padding: 10px;
        background-color: cadetblue;
    }

    .todobox:hover {
        cursor: pointer;
        background-color: darkcyan;
    }

    #btnDelete {
        float:right;
        background-color:darkred;
    }
</style>