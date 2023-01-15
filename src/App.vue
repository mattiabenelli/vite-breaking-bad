<script>
import axios from 'axios';
import YugiCard from "./components/YugiCard.vue";
import YugiList from "./components/YugiList.vue";

import { store } from './store.js'

export default {
  components:{
    YugiCard,
    YugiList,
  },
  data(){
    return{
      store
    }
  },
  beforeMount(){
    this.getCard();
  },
  methods:{
    getCard(){
      axios.get(store.url).then((response) => {
      store.YugiList = (response.data.data)
      })
    }
  }
}
</script>

<template lang="">
  <main>
    <YugiList></YugiList>
  </main>
</template>

<style lang="scss">
  @use './styles/generals.scss' as *
</style>
