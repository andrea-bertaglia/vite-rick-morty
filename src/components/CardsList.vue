<script>
import CardItem from '../components/CardItem.vue';

export default {
    components: {
        CardItem,
    },
    props: {
        // passo l'array da App.vue
        cardsArray: Array,
    },
}
</script>

<template>


    <div class="container">
        <div class="row row-cols-4">
            <div class="col" v-for="card in cardsArray">

                <CardItem :cardObj="card" />
            </div>
        </div>
    </div>
</template>

<script scoped lang="scss">
</script>