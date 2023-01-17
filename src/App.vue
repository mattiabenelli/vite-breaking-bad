<script>
import YugiCard from "./components/YugiCard.vue";
import YugiList from "./components/YugiList.vue";
import YugiSelect from "./components/YugiSelect.vue";

import { store } from './store.js'

export default {
  components:{
    YugiCard,
    YugiList,
    YugiSelect,
  },
  data(){
    return{
      store
    }
  },
  methods:{
    },
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
