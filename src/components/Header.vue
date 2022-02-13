<template>
  <header>
    <select name="genre" @change="$emit('genre-select', $event.target.value)">
      <option value="null">Choose</option>
      <option
        v-for="(album, index) in albumGenre"
        :key="index"
        :value="album.genre.toLowerCase()"
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
  data() {
    return {};
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