<template>
  <div :class="todo.status" @click="toggleStatus">
    {{ todo.content }}
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  data() {
    return {
      content: ""
    };
  },
  methods: {
    toggleStatus() {
      this.todo.status =
        this.todo.status === "incomplete" ? "complete" : "incomplete";
    }
  }
};
</script>

<style scoped>
.complete {
  font-style: italic;
  text-decoration: line-through;
}
</style>
