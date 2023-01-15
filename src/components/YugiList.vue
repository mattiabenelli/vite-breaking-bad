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
    <div class="border-container">
        <div class="container-cards">
            <div class="card-counter"></div>
            <div class="row-table">
                <YugiCard v-for="(item,index) in store.YugiList" :key="index" :card="item"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    .container-cards{
        width: 95%;
        margin: 0 auto;
    }
    .border-container{
        background-color: white;
        width: 80%;
        margin: 0 auto;
        padding: 20px 0;
    }
  
</style>