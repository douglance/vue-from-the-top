<template>
  <div>
    <input v-model="content" />
    <button @click="add">Add</button>
  </div>
</template>

<script>
export default {
  name: "TodoInput",
  data() {
    return {
      content: ""
    };
  },
  methods: {
    add() {
      this.$emit("add", this.content);
    }
  }
};
</script>

<style></style>
