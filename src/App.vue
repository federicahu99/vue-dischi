<template>
  <div>
    <BaseHeader :selectedOption="optionGenre" @change-genre="setGenre" />
    <BaseMain :albums="albumList" :selectedGenre="selectedGenre" />
  </div>
</template>

<script>
import BaseHeader from "./components/BaseHeader.vue";
import BaseMain from "./components/BaseMain.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    BaseHeader,
    BaseMain,
  },
  data() {
    return {
      loading: false,
      api: "https://flynn.boolean.careers/exercises/api/array/music",
      albumList: [],
      selectedGenre: "",
      genreList: []
    };
  },
  methods: {
    getAlbums() {
      this.loading = true;
      axios
        .get(this.api)
        .then((res) => {
          this.albumList = res.data.response;
          const genres = [];
          this.albumList.forEach((album) => {
            if (!genres.includes(album.genre)) {
              genres.push(album.genre);
            }
          });
          this.loading = false;
        })
        .catch((err) => {
          console.log(err);
        });
    },
    setGenre(genre) {
      this.selectedGenre = genre;
    },
  },
  mounted() {
    this.getAlbums();
  },
};
</script>

<style lang="scss">
@import "./assets/scss/style.scss";
</style>
