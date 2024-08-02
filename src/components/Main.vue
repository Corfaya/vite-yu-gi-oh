<script>
import Cards from './partials/Cards.vue';
import CounterFoundCards from './partials/CounterFoundCards.vue';
import { store } from '../store';
export default {
    components: {
        Cards,
        CounterFoundCards
    },
    data() {
        return {
            store
        }
    },
    methods: {
        sendArchetype(){
            this.$emit('filter')
        }
    }
}
</script>
<template>
    <main class="py-50">
        <div class="d-flex flex-justify-center">
            <!-- Select anche @change="$emit('nome evento da richiamare = filter')" -->
            <select class="select-style" name="arch" id="arch" v-model="store.archetypeCard" @change="sendArchetype()">
                <option value="">Select archetype</option>
                <option v-for="arch, i in store.archetypeList" :key="`ar-${i}`" :value="arch.archetype_name">{{arch.archetype_name}}</option>
            </select>
        </div>
        <div class="card-container mx-auto rounded-20">
            <CounterFoundCards />
            <div class="d-flex flex-wrap flex-justify-center p-20">
                <Cards :cardsArr="store.cardList" />
            </div>
        </div>
    </main>
</template>
<style lang="scss" scoped>
@use "../styles/partials/vars" as *;

main {
    background-color: $background_color;

    .card-container {
        background-color: white;
        width: 1000px;
        max-width: 1000px;

        .bg-dark {
            background-color: $bg_dark;
        }
    }
}
</style>