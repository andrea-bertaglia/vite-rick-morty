<script>
export default {
    props: {
        // passo l'oggetto da CardsList.vue
        cardObj: Object,
    },
}
</script>

<template>
    <h5>{{ cardObj.name }}</h5>
</template>

<style scoped lang="scss"></style>