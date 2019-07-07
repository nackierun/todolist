<template>
  <div id="app">
    <ToDos v-bind:ToDos="todos" v-on:del-todo="deleteToDo" />
  </div>
</template>

<script>
import ToDos from './components/ToDos';

export default {
  name: 'app',
  components: {
    ToDos
  },
  data(){
    return {
      todos:[
        {
          id:1,
          title:"ToDo One",
          completed: false
        },
        {
          id:2,
          title:"ToDo Two",
          completed: false
        },
        {
          id:3,
          title:"ToDo Three",
          completed: false
        },
      ]
    }
  },
  methods:{
    deleteToDo(id){
      this.todos = this.todos.filter(ToDos => ToDos.id !== id);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
