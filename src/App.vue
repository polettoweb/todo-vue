<template>
    <div class="container">
        <app-header :todoCount="todos.length" :maxTodos="maxTodos"></app-header>
        <app-new-todo @todoAdded="newTodo"></app-new-todo>
        <app-todo-grid :todos="todos" @todoDeleted="deleteTodo"></app-todo-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-success">Info: Click on a todo to delete it</div>
            </div>
        </div>
    </div>
</template>

<script>
import TodoGrid from "./components/TodoGrid.vue";
import NewTodo from "./components/NewTodo.vue";
import Header from "./components/Header.vue";
export default {
  data: function() {
    return {
      todos: ["Just a todo to visualise something"],
      maxTodos: 10
    };
  },
  methods: {
    newTodo(todo) {
      if (this.todos.length >= this.maxTodos) {
        return alert(
          "Maximum numbers of todos reached. Please delete a todo first!"
        );
      }
      this.todos.push(todo);
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    }
  },
  components: {
    appTodoGrid: TodoGrid,
    appNewTodo: NewTodo,
    appHeader: Header
  }
};
</script>

<style>
</style>
