<template>
  <div id="app">
    <!-- TODO passa solo generi -->
    <Header :genres="genres" @genre-option="searchGenre" />
    <main>
      <section id="albums">
        <div class="container">
          <AlbumCard
            v-for="(album, index) in filteredByGenre"
            :key="index"
            :album-poster="album.poster"
            :album-title="album.title"
            :album-author="album.author"
            :album-year="album.year"
          />
        </div>
      </section>
    </main>
  </div>
</template>

<script>
import AlbumCard from "./components/AlbumCard.vue";
import Header from "./components/Header.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    AlbumCard,
    Header,
  },
  data() {
    return {
      selectedGenre: undefined,
      albums: [],
      genres: [],
    };
  },
  computed: {
    filteredByGenre() {
      const selectedGenre = this.selectedGenre;
      return this.albums.filter((album) => {
        return album.genre.includes(selectedGenre);
      });
    },
  },
  methods: {
    getAlbums() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((res) => {
          this.albums = res.data.response;
          console.log(this.albums);
          this.getGenres();
        });
    },
    searchGenre(selectedGenre) {
      this.selectedGenre = selectedGenre;
      console.log("Selected Genre:" + this.selectedGenre);
    },
    getGenres() {
      this.albums.forEach((album) => {
        const { genre } = album;
        if (!this.genres.includes(genre)) {
          this.genres.push(genre);
        }
      });
    },
  },
  mounted() {
    this.getAlbums();
  },
};
</script>

<style lang="scss">
@import "./assets/sass/style.scss";
#albums {
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
