<script>
export default {
    props: {
        // passo il valore di isLoading da App.vue
        isLoading: Boolean,
    }
}
</script>

<template>
    <h1 v-if="isLoading" class="text-center">LOADING...</h1>
</template>

<style scoped lang="scss"></style>