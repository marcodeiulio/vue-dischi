<template>
  <header>
    <select name="genre" id="genre-select">
      <option value="null">Choose</option>
      <option
        v-for="(album, index) in albumGenre"
        :key="index"
        :value="album.genre"
      >
        {{ album.genre }}
      </option>
    </select>
  </header>
</template>

<script>
export default {
  name: "Header",
  props: ["albumGenre"],
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