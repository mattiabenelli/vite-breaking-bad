<script>
import { store } from '../store.js'

export default {
    data(){
        return{
            store
        }
    },
    methods:{

    }
}
</script>

<template lang="">
    <select v-model="store.selectedGenre" @change="$emit('filter')">
        <option v-for="(item,index) in store.YugiSelect" :value="item.archetype_name" :key="index" > {{ item.archetype_name }} </option>
    </select>
</template>

<style lang="">
    
</style> 