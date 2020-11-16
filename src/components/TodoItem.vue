<template>
  <div class="todo-item" v-bind:class="{'is-completed':todo.completed}">
    <!-- <h1>{{todo.title}}</h1> -->
    <p>
        <input type="checkbox" v-on:change="markComplete"> 
        {{todo.title}}
    </p>
  </div>
</template>

<script>
export default {
  name: "todo-item",
  props: ["todo"], 
  methods: {
      markComplete(){
        console.log('in items'); 
        this.$emit('toggle-completed-in-todo-item', 0); 
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