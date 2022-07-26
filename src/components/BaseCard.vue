<template>
  <div class="single-card">
    <img :src="album.poster" :alt="album.title" />
    <h2>{{ album.title }}</h2>
    <h4>{{ album.author }}</h4>
    <h4>{{ album.year }}</h4>
  </div>
</template>

<script>
export default {
  name: "BaseCard",
  props: {
    album: Object,
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/var";

.single-card {
  display: flex;
  flex-direction: column;

  img {
    object-fit: cover;
    object-position: center;
    height: 150px;
    width: 150px;
  }

  h2,
  h4 {
    text-align: center;
    background-color: $primary-color;
  }

  h2 {
    margin: 10px 0;
    color: white;
  }

  h4 {
    color: grey;
    font-weight: 400;
  }
}
</style>