<template>
    <div class="AddTextBox">
        <input 
            class="textbox"
            type="text" 
            placeholder="Write some text" 
            v-model="todoText"
            />
        <br>
        <button id="btnAdd" @click="addTodo">Add</button>
    </div>
</template>

<script>
export default {
    data() {
      return { 
        todoText: ""
      }
    },
    methods: {
        addTodo() {
            if(this.todoText == "") {
                alert("Please enter some text.");
            } else {
                this.$emit('addTodo', this.todoText);
            }
        }
    }
}
</script>

<style>
    .AddTextBox{
        margin: auto;
        width: 50%;
        padding: 10px;
    }

    #btnAdd {
        padding: 10px;
        width: 80%;
    }

    .textbox {
        padding: 10px;
        width: 100%;
        margin-bottom: 10px;
    }
</style>