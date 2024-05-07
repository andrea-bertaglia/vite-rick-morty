<script>
export default {
    props: {
        // passo l'oggetto da CardsList.vue
        cardObj: Object,
    },
}
</script>

<template>
    <span>Trovati <strong class="text-decoration-underline">{{ cardObj.length }}</strong>
        elementi</span>
</template>