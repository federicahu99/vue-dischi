<template>
  <div class="single-card">
    <img :src="album.poster" :alt="album.title">
    <h2> {{ album.title }}  </h2>
    <h3> {{ album.author }} </h3>
    <h3> {{ album.year }} </h3>
  </div>
</template>

<script>
export default {
    name: "BaseCard",
    props: {
        album: Object,
    }
}
</script>

<style lang="scss" scoped>
    .single-card {
        display: flex;
        flex-direction: column;

        img {
            object-fit: cover;
            object-position: center;
            height: 150px;
            width: 150px;
        }
    }
</style>