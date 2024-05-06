<script>
import CardItem from '../components/CardItem.vue';

export default {
    components: {
        CardItem,
    },
    props: {
        cardsArray: Array,
    },
}
</script>

<template>
    <h3>Questo è CardsList.vue</h3>

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