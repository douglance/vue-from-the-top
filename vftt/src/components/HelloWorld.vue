<template>
  <div class="hello">
    <h1>{{ message }}</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: ["message"]
};
</script>

<style>
.hello {
  color: green;
}
</style>
