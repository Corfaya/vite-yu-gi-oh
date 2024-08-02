<script>
import { store } from '../../store';
export default {
    data() {
        return {
            store
        }
    }
}
</script>
<template>
    <div class="bg-dark rounded-t-20">
        <p class="ms-30 py-20">Found {{ store.cardList.length }} cards</p>
    </div>
</template>
<style lang="scss">
p {
    color: white;
}
</style>