<template>
  <header>
    <OptionSelect :options="genres" @change-option="genreOption" />
  </header>
</template>

<script>
import OptionSelect from "./OptionSelect.vue";
export default {
  name: "Header",
  components: {
    OptionSelect,
  },
  props: ["genres"],
  methods: {
    genreOption(selectedGenre) {
      this.$emit("genre-option", selectedGenre);
    },
  },
};
</script>

<style scoped lang="scss">
@import "../assets/sass/_vars.scss";
header {
  background-color: $secondary-color;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
