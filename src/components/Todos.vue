<template>
  <div>
    <h1>TODOS</h1>

    <div v-bind:key="todo.id" v-for="todo in kera">
      <TodoItem
        v-bind:todo="todo"
        v-on:toggle-completed-in-todo-item="toggler2(todo)"
        v-on:del-todo="$emit('del-app', todo.id)"
      />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  name: "TODOS 2",
  components: {
    TodoItem
  },
  props: ["kera"], 
  methods: {
      toggler2(td){
        console.log('in todos');
        console.log(td.id); 
        this.$emit('toggle-completed-in-todos', td.id);
        console.log('done in todos'); 
      }
  }
};
</script>

<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px #ccc dotted;
}
.is-complete {
  text-decoration: line-through;
}
.del {
  background: #ff0000;
  color: #fff;
  border: none;
  padding: 5px 9px;
  border-radius: 50%;
  cursor: pointer;
  float: right;
}
</style>