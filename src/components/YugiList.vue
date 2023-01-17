<script>
import axios from 'axios';
import YugiCard from './YugiCard.vue';
import YugiSelect from './YugiSelect.vue';
import { store } from '../store.js'

export default {
    components:{
        YugiCard,
        YugiSelect
    },
    data(){
        return{  
            store
        }
    },
    methods:{
        getArchetype(){
            axios.get(store.urlArchetypeName).then((response) => {
            store.YugiSelect = (response.data)
        });
        },
        getCard(){
            let myUrl = `${store.url}${store.selectedGenre}`

            axios.get(myUrl).then((response) => {
            store.YugiList = (response.data.data)
            })
        }
    },
    beforeMount(){
    this.getCard();
    this.getArchetype();
  },
}
</script>

<template lang="">
    <YugiSelect @filter="getCard"/>
    <div class="border-container">
        <div class="container-cards">
            <div class="card-counter">trovate {{store.YugiList.length}} carte</div>
            <div class="row-table">
                <YugiCard v-for="(item,index) in store.YugiList" :key="index" :card="item"/>
            </div>
        </div>
    </div>
</template>

<style lang="scss">
    @use '../styles/partials/variables' as * ;
    @use '../styles/partials/mixins' as * ;


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
    .card-counter{
        background-color: #212529;
        color: white;
        padding: 10px 20px;
    }
  
</style>