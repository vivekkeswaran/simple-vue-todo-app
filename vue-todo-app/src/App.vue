<template>
  <div class="App">
    <div class="Wrapper">
      <TodoHeader />
      <TodoInput :iText="message" @textChanged="message=$event" />
      <div class="todoWrapper" id="todoScroll">
        <ul v-for="todo in todos" :key="todo.id">
            <todo-list :id="todo.id" :text="todo.text" />
        </ul> 
      </div>
    </div>
  </div>
</template>

<script>
import TodoHeader from "./components/TodoHeader";
import TodoInput from "./components/TodoInput";
import TodoList from "./components/TodoList"

export default {
  name: "App",
  components: {
    TodoHeader, TodoInput, TodoList
  },
  data() {
    return {
      message: "",
      todos: [
        {id: 1, text: "Meeting at 11am"},
        {id: 2, text: "Car Wash today"}
      ],
      nextId: 3
    }
  },
  methods: {
    addTodo(todoText) {
      let newId = this.nextId++;
      this.todos.push({id: newId, text: todoText});
    },
    removeTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    }
  }
};
</script>

<style>
@import './assets/App.css';

</style>
