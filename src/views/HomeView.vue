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
      todos: [
        {
          title: "Task 1",
          description: "Description 1",
          done: true,
        },
        {
          title: "Task 2",
          description: "Description 2",
          done: false,
        },
        {
          title: "Task 3",
          description: "Description 3",
          done: false,
        },
      ],
    };
  },
  methods: {
    addItem(newItem) {
      this.todos.push(newItem);
    },
    deleteItem(item) {
      const index = this.todos.indexOf(item);
      this.todos.splice(index, 1);
    },
    toggleDone(item) {
      const index = this.todos.indexOf(item);
      this.todos[index].done = !this.todos[index].done;
    },
  },
};
</script>
