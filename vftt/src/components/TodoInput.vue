<template>
  <b-form inline @submit="add">
    <b-input-group class="mt-3">
      <template v-slot:append>
        <b-button @click="add" variant="success"><b-icon-plus /></b-button>
      </template>
      <b-form-input v-model="content" placeholder="Enter Todo" />
    </b-input-group>
  </b-form>
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
