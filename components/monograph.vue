<template>
  <div>
    <div class="d-block text-center cursor-pointer" @click="click">
      <h1>{{ symbol }}</h1>
      <h3>{{ name }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "monograph",
  props: [
    "id",
    "symbol",
    "name",
  ],
  methods: {
    click() {
      this.$emit("mgClick", this)
    },
  },
}
</script>

<style scoped>
.cursor-pointer {
  cursor: pointer;
}
</style>
