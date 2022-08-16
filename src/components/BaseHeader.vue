<template>
  <header>
    <img
      src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png"
      alt="Spotify logo"
    />
    <BaseSelect :options="genreList" @change-option="changeOption" />
  </header>
</template>

<script>
import BaseSelect from "./BaseSelect.vue";

export default {
  name: "BaseHeader",
  components: { BaseSelect },
  props: { genreList: Array },
  methods: {
    changeOption(value) {
      this.$emit("change-genre", value)
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/var";
header {
  height: 50px;
  padding: 10px 20px;
  background-color: $primary-color;
  display: flex;
  justify-content: space-between;

  img {
    border-radius: 50%;
  }
}
</style>