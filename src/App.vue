<template>
  <div id="app">
    <Header />
    <ListManager  v-on:add-todo="createTodo" v-on:remove-todo="removeTodo" v-on:clear-todo="clearTodo" />
    <Todos v-bind:todos="todos"/>
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Todos from './components/Todos';
import ListManager from './components/ListManager';
import uuid from 'uuid';

export default {
  name: 'app',
  components: {
    Header,
    Todos,
    ListManager
  },
  data() {
    return {
      todos: [],
      num: 0,
    }
  },
  methods: {
    createTodo() {
      const newTodo = {
        id: uuid.v4(),
        title: 'Task number ',
        number: this.num,
        }
      this.num++; 
      this.todos = [...this.todos, newTodo];
    },
    removeTodo(num) {
      this.todos.splice(this.todos.indexOf(num), 1);
      this.num--;
      if(this.num < 0) {
        this.num = 0;
      }
    },
    clearTodo() {
      this.num = 0;
      this.todos = [];
    }
  }
}
</script>

<style>
 *{
   box-sizing: border-box;
   margin: 0;
   padding: 0;
 }

 body {
   font-family: Arial, Helvetica, sans-serif;
   line-height: 1.4;
 }
</style>
