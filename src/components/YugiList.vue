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
    <div class="container-cards">
        <div class="row-table">
            <YugiCard v-for="(item,index) in store.YugiList" :key="index" :card="item" />
        </div>
    </div>
</template>

<style lang="scss">
    .container-cards{
        width: 80%;
        margin: 0 auto
    }
  
</style>