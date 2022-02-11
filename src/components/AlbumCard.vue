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
  height: 280px;
  width: 150px;
  padding: 10px;
  margin: 20px;
  color: white;
  text-align: center;

  h3 {
    margin-bottom: 10px;
  }
  p {
    color: grey;
    font-size: 0.85rem;
    font-weight: lighter;
  }

  img {
    width: 130px;
    height: auto;
  }
}
</style>