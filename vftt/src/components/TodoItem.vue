<template>
  <b-list-group-item
    button
    :class="todo.status"
    class="d-flex justify-content-between align-items-center"
    @click="toggleStatus"
  >
    {{ todo.content }}
    <b-button
      size="sm"
      variant="danger"
      class="pull-right"
      @click="$emit('remove', index)"
      ><b-icon-trash
    /></b-button>
  </b-list-group-item>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo", "index"],
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
