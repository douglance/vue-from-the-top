<template>
  <div id="app">
    <b-card class="m-2">
      <TodoInput @add="add" />
    </b-card>
    <b-card class="m-2">
      <b-list-group>
        <TodoItem
          v-for="(todo, index) in sortedTodos"
          :todo="todo"
          :index="index"
          :key="todo.content"
          @remove="remove"
        />
      </b-list-group>
    </b-card>
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
    },
    remove(index) {
      this.todos.splice(index, 1);
    }
  }
};
</script>
