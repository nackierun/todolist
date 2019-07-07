<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <div @click="$emit('del-todo', todo.id)" class="del">X</div>
        </p>
    </div>
</template>

<script>
export default {
    name: "ToDoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
   .todo-item{
       background-color: aliceblue;
       padding: 10px;
       border-bottom: 1px #ccc dotted;
   }
   .is-complete{
       text-decoration-line: line-through;
   }
   .del{
       background-color: crimson;
       color: #ffffff;
       border: none;
       padding: 5px 9px;
       border-radius: 50%;
       cursor: pointer;
       float: right;
   }
</style>
