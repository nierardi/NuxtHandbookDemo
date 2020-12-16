<template>
  <div class="main" v-if="mg">
    <button class="btn btn-dark" @click="backClick">Back to List</button>
    <h1 class="pb-3">{{ mg.name }}</h1>
    <table class="table">
      <tr>
        <th scope="col">Property</th>
        <th scope="col">Value</th>
      </tr>
      <tr>
        <td>Id</td>
        <td>{{ mg.id }}</td>
      </tr>
      <tr>
        <td>Name</td>
        <td>{{ mg.name }}</td>
      </tr>
      <tr>
        <td>Symbol</td>
        <td>{{ mg.symbol }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: "monographDetails",
  props: [
    "mg",
  ],
  methods: {
    backClick() {
      this.$emit("backClick");
    }
  }
}
</script>

<style scoped>

</style>
