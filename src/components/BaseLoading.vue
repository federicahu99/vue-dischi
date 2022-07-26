<template>
  <div class="loading">
    Loading...
  </div>
</template>

<script>
export default {
    name: 'BaseLoading'
}
</script>

<style lang="scss" scoped>
.loading{
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    text-align: center;
    font-size: 40px;
    position: fixed; 
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(235,235,230, 0.7);
}
</style>