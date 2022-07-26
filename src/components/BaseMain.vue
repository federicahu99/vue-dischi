<template>
  <div class="flex container">
    <BaseLoading v-if="loading" />
    <BaseCard 
        v-else
        v-for="(album, i) in albumList" 
        :key="i" 
        :album="album" 
        class="cards-container"/>
  </div>
</template>

<script>
import BaseCard from "../components/BaseCard.vue";
import axios from "axios";
import BaseLoading from "../components/BaseLoading.vue"

export default {
  components: {
    BaseCard,
    BaseLoading,
  },
  data() {
    return {
      loading: false,
      api: "https://flynn.boolean.careers/exercises/api/array/music",
      albumList: [],
    };
  },
  methods: {
    getAlbums() {
      this.loading= true;
      return axios
        .get(this.api)
        .then((res) => {
          this.albumList = res.data.response;
          console.log(res.data);
          this.loading= false;
        })
        .catch((err) => {
          console.log(err)
          })
        .then(() => {
          this.loading= false;
        });
    },
  },
  mounted() {
    this.getAlbums();
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/var";
    .flex {
        display: flex;
        flex-wrap: wrap;

        .cards-container {
            flex-basis: calc(100% / 5 - 60px);
            background-color: $primary-color;
            margin: 10px 0 10px 10px;
            padding: 10px;
        }
    }

</style>