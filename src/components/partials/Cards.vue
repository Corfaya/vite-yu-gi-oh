<script>
import { store } from '../../store';
export default {
    props: {
        cardsArr: Array
    },
    data() {
        return {
            store
        }
    }
}
</script>
<template>
    <div class="card card-col m-10x5" v-for="card in cardsArr" :key="card.id">
        <div class="img-box d-flex flex-justify-center">
            <img class="mxw-100 mx-auto" :src="card.card_images[0].image_url" alt="card">
        </div>
        <p class="name text-center p-5x20">{{card.name}}</p>
        <p class="card-type text-center pb-10">{{ card.type }}</p>
        <p class="card-type text-center pb-10">{{ card.archetype }}</p>
    </div>
</template>
<style lang="scss" scoped>
@use "../../styles/partials/vars" as *;
    .card {
        background-color: $background_color;
        @media screen and (max-width: 800px){
                width: calc(100% / 4 - 20px);
        }
        .img-box {
            img {
                width: 100%;
                height: 100%;
                object-fit: contain;
            }        
        }
        p.name {
            color: white;
            font-weight: 800;
        }
    }
</style>