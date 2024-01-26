<script setup>
import AddNewItem from "../components/AddNewItem.vue";
import ToDoItem from "../components/ToDoItem.vue";
</script>

<template>
  <div class="container">
    <h1 class="text-center mb-3">Todo List</h1>
    <AddNewItem @add-item="addItem" />
    <h4>Your Todos</h4>
    <div v-if="todos.length === 0">No Todos to display</div>
    <div v-else>
      <ToDoItem
        v-for="item in todos"
        v-bind:item="item"
        @delete-item="deleteItem"
        @toggle-done="toggleDone"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: localStorage.getItem("todos")
        ? JSON.parse(localStorage.getItem("todos"))
        : [],
    };
  },

  methods: {
    addItem(newItem) {
      this.todos.push(newItem);
      localStorage.setItem("todos", JSON.stringify(this.todos));
    },
    deleteItem(item) {
      const index = this.todos.indexOf(item);
      this.todos.splice(index, 1);
      localStorage.setItem("todos", JSON.stringify(this.todos));
    },
    toggleDone(item) {
      const index = this.todos.indexOf(item);
      this.todos[index].done = !this.todos[index].done;
      localStorage.setItem("todos", JSON.stringify(this.todos));
    },
  },
};
</script>
