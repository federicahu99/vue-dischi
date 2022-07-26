<template>
  <header>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="Spotify logo">
  </header>
</template>

<script>
export default {
    name: 'BaseHeader'
}
</script>

<style lang="scss" scoped>
@import "../assets/scss/var";
    header {
        height: 50px;
        padding: 10px 20px;
        background-color: $primary-color;

        img {
            border-radius: 50%;
        }
    }
</style>