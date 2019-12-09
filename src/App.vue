<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" v-on:del-todo="DeleteTodo" />
    <AddTodo />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./layout/Header";
import AddTodo from "./components/AddTodo";
export default {
  name: "app",
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Todo 1", completed: false },
        { id: 2, title: "Todo 2", completed: false },
        { id: 3, title: "Todo 3", completed: false }
      ]
    };
  },
  methods: {
    DeleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
