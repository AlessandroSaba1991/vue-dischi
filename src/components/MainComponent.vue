<template>
  <main class="py_5">
      <Albums />
  </main>
</template>

<script>
import Albums from './AlbumsComponent.vue'

export default {
    name: 'MainComponent',
    components:{
        Albums
    }
}
</script>

<style lang="scss" scoped>
main{
    height: calc(100vh - 72px);
    background-color: $bgMain;
}
</style>