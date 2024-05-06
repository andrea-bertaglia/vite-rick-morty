<script>
import CardItem from '../components/CardItem.vue';

export default {
    components: {
        CardItem,
    },
    props: {
        // passo l'array da App.vue
        cardsArray: Array,
        // passo il valore di isLoading da App.vue
        isLoading: Boolean,
    },
}
</script>

<template>


    <div v-if="isLoading" class="container">
        <div class="row row-cols-4">
            <div class="col g-3 my-4" v-for="card in cardsArray">

                <CardItem :cardObj="card" />
            </div>
        </div>
    </div>
</template>

<script scoped lang="scss">
</script>