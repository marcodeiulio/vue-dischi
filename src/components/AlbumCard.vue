<template>
  <div id="album_card">
    <figure>
      <img :src="albumPoster" :alt="albumTitle" />
      <figcaption>
        <h3>{{ albumTitle }}</h3>
        <p>{{ albumAuthor }}</p>
        <p>{{ albumYear }}</p>
      </figcaption>
    </figure>
  </div>
</template>

<script>
export default {
  name: "AlbumCard",
  props: [
    "albumPoster",
    "albumTitle",
    "albumAuthor",
    "albumGenre",
    "albumYear",
  ],
};
</script>

<style scoped lang="scss">
#album_card {
  background-color: #2e3a46;
  height: 250px;
  width: 150px;
  padding: 5px;
  margin: 20px;
  color: white;

  img {
    width: 140px;
    height: auto;
  }
}
</style>