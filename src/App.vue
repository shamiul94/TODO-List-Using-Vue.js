<template>
  <div id="app">
    <Todos
      v-bind:kera="todos"
      v-on:toggle-completed-in-todos="$id => {toggler(todos, $id)}"
    />
    <Todos v-bind:kera="todos" />
    <h1>my test {{todos[0]['title']}}</h1>
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
          id: 1,
          title: "todo one",
          completed: true
        },
        {
          id: 2,
          title: "todo two",
          completed: false
        }
      ]
    };
  }, 
  methods: {
    toggler(tds, id){
      console.log('in baap');
      console.log(tds); 
      console.log(id); 
      console.log(this.todos[id]['completed']); 
      this.todos[id]['completed'] = !this.todos[id]['completed'];
      console.log(this.todos[id]['completed']); 
      console.log('successful'); 
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
