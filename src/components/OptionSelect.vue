<template>
  <select v-model="selectedOption" @change="changeOption">
    <option value="null">Sort by Genre</option>
    <option v-for="(option, index) in options" :key="option.id || index">
      {{ option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "GenreSelect",
  props: {
    options: Array,
  },
  data() {
    return {
      selectedOption: null,
    };
  },
  methods: {
    changeOption() {
      this.$emit("change-option", this.selectedOption);
    },
  },
};
</script>

<style></style>
