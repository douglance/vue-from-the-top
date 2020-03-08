<template>
  <div>
    {{ todo.content }}
  </div>
</template>

<script>
export default {
  name: "TodoInput",
  props: ["todo"],
  data() {
    return {
      content: ""
    };
  }
};
</script>

<style></style>
