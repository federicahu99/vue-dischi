<template>
    <div class="flex"> 
        <BaseCard v-for="album in albumList" 
        :key="album.poster" 
        :album="album"/>
    </div>
</template>

<script>
import BaseCard from '../components/BaseCard.vue'
import axios from 'axios'

export default {
     components: {
     BaseCard,

    },
     data() {
    return {
        api: 'https://flynn.boolean.careers/exercises/api/array/music',
        albumList: [],
        }
    }, methods: {
        getAlbums(){
            return axios.get(this.api)
            .then(res => this.albumList(res.data))
            .catch(err => console.log(err))
        }
    }, mounted(){
        this.getAlbums()
    }
}

</script>

<style>

</style>