<template>
  <header class="d-flex py-3 px-4">
      <Logo />
      <Select v-model="typeGenere" @selectGenere="selectGenere"/>
  </header>
</template>

<script>
import Logo from './LogoComponent.vue'
import Select from './SelectComponent.vue'
import state from '@/state'

export default {
    name:'HeaderComponent',
    components:{
        Logo,
        Select
    },
    data(){
        return{
            typeGenere:''
        }
    },
    methods:{
        selectGenere(){
            state.selectGenere = this.typeGenere;
        }
    }
}
</script>


<style lang="scss" scoped>
header{
    background-color: $bgHeader;
    justify-content: space-between;
    align-items: center;
}
</style>