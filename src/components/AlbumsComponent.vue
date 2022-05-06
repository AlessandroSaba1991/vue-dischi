<template>
  <section v-if="!loading" class="albums py-3">
    <div class="container">
      <div
        class="
          row
          gy-4
          gx-5
          row-cols-1 row-cols-md-2 row-cols-lg-4 row-cols-xxl-5
        "
      >
        <Album :album="album" v-for="(album, index) in filtered" :key="index" />
      </div>
    </div>
  </section>
  <Loading v-else />
</template>

<script>
import axios from "axios";
import Album from "./AlbumItem.vue";
import Loading from "./LoadingComponent.vue";
import state from "@/state";

export default {
  name: "AlbumsComponent",
  components: {
    Album,
    Loading,
  },
  data() {
    return {
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
      albums: null,
      error: null,
      loading: true,
    };
  },
  computed: {
    filtered() {
      if (state.selectGenere != "" && state.selectAuthor != "") {
        return this.albums.filter(album => album.genre === state.selectGenere && album.author === state.selectAuthor);
      } else if (state.selectGenere != "") {
        return this.albums.filter(album => album.genre === state.selectGenere);
      } else if (state.selectAuthor != "") {
        return this.albums.filter(album => album.author === state.selectAuthor);
      } else {
        state.Albums = this.albums
        return this.albums;
      }
    },
  },
  methods: {
    APICall() {
      axios
        .get(this.API_URL)
        .then((response) => {
          this.albums = response.data.response;
          this.loading = false;
        })
        .catch((error) => {
          this.error = `Sorry,We've a problem ${error} `;
        });
    },
  },
  mounted() {
    this.APICall();
  },
};
</script>

<style>
</style>