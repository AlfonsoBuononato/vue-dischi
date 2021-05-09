<template>
  <div class="select">
    <label for="gen">Filter by gender:</label>
    <select
      v-model="valore"
      name="gen"
      id="gen"
      @change="$emit('filtra', valore)"
    >
      <option value="all">all</option>
      <option
        v-for="(element, index) in select.genere"
        :key="index"
        :value="element"
        >{{ element }}</option
      >
    </select>
  </div>
</template>

<script>
export default {
  name: "Select",
  props: ["select"],
  data() {
    return {
      valore: "all",
    };
  },
};
</script>

<style></style>
