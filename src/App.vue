<template>
  <div id="app">
    <main>
      <section id="albums">
        <div class="container">
          <AlbumCard
            v-for="(album, index) in albums"
            :key="index"
            :album-poster="album.poster"
            :album-title="album.title"
            :album-author="album.author"
            :album-genre="album.genre"
            :album-year="album.year"
          />
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import AlbumCard from "./components/AlbumCard.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    AlbumCard,
  },
  data() {
    return {
      albums: [],
    };
  },
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.albums = res.data.response;
          console.log(this.albums);
        });
    },
  },
  mounted() {
    this.getAlbums();
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

img {
  max-width: 100%;
}

#albums {
  background-color: #1e2d3b;
  .container {
    width: 1080px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }
}
</style>
