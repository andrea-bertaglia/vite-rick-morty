<script>
export default {
    props: {
        // passo l'oggetto da CardsList.vue
        cardObj: Object,
    },
    computed: {
        image() {
            return this.cardObj.image;
        },
    }
}
</script>

<template>
    <div class="container">
        <img class="ratio ratio-1x1 rounded-circle shadow" :src="image" :alt="`Immagine di ${cardObj.name}`">
        <h4 class="text-center my-3 fw-light fs-5">{{ cardObj.name }}</h4>
        <h5 class="text-center fw-lighter fs-6">{{ cardObj.status }}</h5>
        <h6 class="text-center fw-lighter fs-6">{{ cardObj.species }}</h6>

    </div>


</template>

<style scoped lang="scss"></style>