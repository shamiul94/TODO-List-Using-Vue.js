<template>
  <div id="app">
    <Todos
      v-bind:kera="todos"
      v-on:toggle-completed-in-todos="$id => {toggler(todos, $id)}"
      v-on:del-app="$id=>{deleteTodo($id)}"
    />
    <!-- <Todos v-bind:kera="todos" /> -->
    <!-- <h1>my test {{todos[0]['title']}}</h1> -->
  </div>
</template>

<script>
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: "todo one",
          completed: false
        },
        {
          id: 1,
          title: "todo two",
          completed: false
        },
        {
          id: 2,
          title: "todo three",
          completed: false
        },
        {
          id: 3,
          title: "todo four",
          completed: false
        },
        {
          id: 4,
          title: "todo five",
          completed: false
        },
        {
          id: 5,
          title: "todo six",
          completed: false
        },
        {
          id: 6,
          title: "todo seven",
          completed: false
        }
      ]
    };
  }, 
  methods: {
    toggler(tds, id){
      console.log('in parent');
      console.log(tds); 
      console.log(id); 
      console.log(this.todos[id]['completed']); 
      this.todos[id]['completed'] = !this.todos[id]['completed'];
      console.log(this.todos[id]['completed']); 
      console.log('successful'); 
    }, 
    deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id !== id); 
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
