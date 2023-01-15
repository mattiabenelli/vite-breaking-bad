<script>
import YugiCard from './YugiCard.vue';
import { store } from '../store.js'

export default {
    components:{
        YugiCard
    },
    data(){
        return{
            store
        }
    }
}
</script>

<template lang="">
  <div>
    <YugiCard v-for="(item,index) in store.YugiList" :key="index" :card="item" />
  </div>
</template>

<style lang="">
  
</style>