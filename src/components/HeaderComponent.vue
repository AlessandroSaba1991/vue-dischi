<template>
  <header class="d-flex py-3 px-4">
      <Logo />
      <div class="menu_right text-end">
      <Select v-model="typeGenere" @selectGenere="selectGenere"/>
      <Select-author v-model="typeAuthor" @selectAuthor="selectAuthor" />

      </div>
  </header>
</template>

<script>
import Logo from './LogoComponent.vue'
import Select from './SelectGenereComponent.vue'
import SelectAuthor from './SelectAuthor.vue'
import state from '@/state'

export default {
    name:'HeaderComponent',
    components:{
        Logo,
        Select,
        SelectAuthor
    },
    data(){
        return{
            typeGenere:'',
            typeAuthor:''
        }
    },
    methods:{
        selectGenere(){
            state.selectGenere = this.typeGenere;
        },
        selectAuthor(){
            state.selectAuthor = this.typeAuthor
        }
    },

}
</script>


<style lang="scss" scoped>
header{
    background-color: $bgHeader;
    justify-content: space-between;
    align-items: center;
}
</style>