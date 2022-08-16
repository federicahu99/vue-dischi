<template>
  <div class="flex container">
    <BaseLoading v-if="loading" />
    <BaseCard
      v-else
      v-for="(album, i) in albums"
      :key="i"
      :album="album"
      class="cards-container"
    />
  </div>
</template>

<script>
import BaseCard from "../components/BaseCard.vue";
import BaseLoading from "../components/BaseLoading.vue";

export default {
  components: {
    BaseCard,
    BaseLoading,
  },
  props: {
    albums: Array,
    selectedGenre: String,
  },
  data() {
    return {
      loading: false,
      selectGenre: "",
    };
  },
  computed: {
    getGenre() {
      return this.albums.filter((album) => {
        if(!this.selectGenre) return this.albums
        if (album.genre === this.selectGenre) return true
        else return false
      });
    },
  },
  methods: {
    setGenre() {
      this.$emit("option-changed", this.selectedOption);
    },
  },
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/var";
.flex {
  display: flex;
  flex-wrap: wrap;

  .cards-container {
    background-color: $primary-color;
    margin: 10px 0 10px 10px;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
  }
}
</style>