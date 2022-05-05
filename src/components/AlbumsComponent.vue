<template>
  <section class="albums py-3">
      <div class="container">
          <div class="row gy-4 gx-5 row-cols-5">
              <Album :album="album" v-for="(album, index) in albums" :key="index"/>
          </div>
      </div>
  </section>
</template>

<script>
import axios from 'axios'
import Album from './AlbumItem.vue'


export default {
    name:'AlbumsComponent',
    components:{
        Album
    },
    data(){
        return{
            API_URL:'https://flynn.boolean.careers/exercises/api/array/music',
            albums: null,
            error:null
        }
    },
    methods: {
        APICall(){
            axios.get(this.API_URL)
            .then(response =>{
                this.albums = response.data.response
            })
            .catch(error =>{
                this.error = `Sorry,We've a problem ${error} `
            })
        }
    },
    mounted(){
        this.APICall()
    }
}
</script>

<style>

</style>