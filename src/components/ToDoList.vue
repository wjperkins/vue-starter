<template>
  <div class="todo-list">
    <h1>Todo list</h1>
    <input
      autofocus
      class="todo-input"
      v-model="newTodo"
      placeholder="Add a todo..." 
      @keyup.enter="addTodo"
    />
    <ToDoItem
      v-for="(todo, index) in todos"
      :key="todo"
      :value="todo"
      @delete="deleteTodo(index)"
    />
  </div>
</template>

<script>
import ToDoItem from './ToDoItem.vue'
export default {
  components: { ToDoItem },
  name: 'ToDoList',
  data() {
    return {
      todos: [],
      newTodo: '',
    }
  },
  methods: {
    addTodo() {
      if(this.newTodo.trim()) { 
        this.todos.unshift(this.newTodo);
        this.newTodo = '';
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .todo-list {
    color: #eceff4;
    margin: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .todo-input {
    padding: 10px;
    text-align: center;
    margin-bottom: 10px;
    border: none;
    border-radius: 5px;
    width: 400px;
    color: #2e3440;
    background: #d8dee9;
  }
</style>
