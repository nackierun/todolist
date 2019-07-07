<template>
    <div>
        <div v-bind:key="ToDo.id" v-for="ToDo in ToDos">
        <ToDoItem v-bind:todo="ToDo" v-on:del-todo="$emit('del-todo', ToDo.id)" />
        </div>
    </div>
</template>
<script>
import ToDoItem from './ToDoItem';
export default {
    name: "ToDos",
    components:{
        ToDoItem
    },
    props: ["ToDos"]
}
</script>

<style scoped>

</style>


