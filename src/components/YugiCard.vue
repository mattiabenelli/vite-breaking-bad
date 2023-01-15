<script>
export default {
  props:{
    card: Object,
  }
}
</script>

<template lang="">
    <div class="card">
        <div><img :src="card.card_images[0].image_url" alt=""></div>
        <div class="card-description">
            <div>{{ card.name }}</div>
            <div>{{ card.archetype }}</div>
        </div>
    </div>
</template>

<style lang="scss">
  .card{
    width: calc(100% / 5 - 20px);
    background-color: orange;
    margin: 10px;
        img{
            width: 100%;
        }
  }
  .card-description{
    text-align: center;
    padding: 10px 0;
  }
</style>