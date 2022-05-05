<template>
  <header class="py-3 px-4">
      <Logo />
  </header>
</template>

<script>
import Logo from './LogoComponent.vue'

export default {
    name:'HeaderComponent',
    components:{
        Logo
    }
}
</script>


<style lang="scss" scoped>
header{
    background-color: $bgHeader;
}
</style>