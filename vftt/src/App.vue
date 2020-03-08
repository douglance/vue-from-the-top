<template>
  <div id="app">
    <TodoInput @add="add" />
    <TodoItem v-for="todo in todos" :todo="todo" :key="todo.content" />
  </div>
</template>

<script>
import TodoInput from "./components/TodoInput.vue";
import TodoItem from "./components/TodoItem.vue";
export default {
  name: "App",
  components: {
    TodoInput,
    TodoItem
  },
  data() {
    return {
      todos: [
        {
          content: "todo1"
        }
      ]
    };
  },
  methods: {
    add(content) {
      this.todos.push({ content });
    }
  }
};
</script>
