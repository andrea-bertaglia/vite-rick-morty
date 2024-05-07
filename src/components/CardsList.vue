<script>
import { store } from "../store";
import CardItem from '../components/CardItem.vue';

export default {
    components: {
        CardItem,
    },
    data() {
        return {
            store,
        }
    },
}
</script>

<template>


    <div class="container">
        <div class="row row-cols-4">
            <div class="col g-3 my-4" v-for="card in this.store.cardsList">

                <CardItem :cardObj="card" />
            </div>
        </div>
    </div>
</template>

<script scoped lang="scss">
</script>