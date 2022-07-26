<template>
    <div class="flex">
        <figure v-for="album in albumList" :key="album.title"> 
            <Card />
        </figure>
    </div>
</template>

<script>
import Card from '../components/BaseCard'
export default {
     components: {
     Card,
  },
     data() {
    return {
        api: 'https://flynn.boolean.careers/exercises/api/array/music',
        albumList: [],
        }
    }, methods: {
        getalbums(){
            return axios.get(this.api)
            .then(res => this.albumList(res.data))
            .catch(err => console.log(err))
        }
    }, mounted(){
        this.getalbums()
    }
}

</script>

<style>

</style>