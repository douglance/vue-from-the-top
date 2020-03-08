<template>
  <div id="app">
    <TodoInput @add="add" />
    <TodoItem v-for="todo in sortedTodos" :todo="todo" :key="todo.content" />
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
    return { todos: [{ content: "Feed the Dog", status: "incomplete" }] };
  },
  computed: {
    sortedTodos() {
      const arr = this.todos;
      return arr.sort(a => (a.status === "incomplete" ? -1 : 1));
    }
  },
  methods: {
    add(content) {
      this.todos.push({ content, status: "incomplete" });
    }
  }
};
</script>
