<template>
  <header>
    <select name="genre" id="genre-select">
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
    </select>
  </header>
</template>

<script>
export default {
  name: "Header",
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