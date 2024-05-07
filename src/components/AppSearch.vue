<script>
import { store } from "../store"
import CounterElements from '../components/CounterElements.vue';
export default {
    components: {
        CounterElements,
    },
    data() {
        return {
            store,
            statusArray: ["All", "Alive", "Dead", "Unknown"]
        }
    },

}
</script>

<template>
    <div class="container py-4">
        <div class="row">

            <div class="d-flex justify-content-between">
                <div>
                    <span class="px-2">Seleziona lo status</span>
                    <select @change="$emit('filter')" v-model="store.selectedStatus">
                        <option :value="status" v-for="status in statusArray">
                            {{ status }}</option>
                    </select>

                </div>

                <CounterElements :cardObj="this.store.cardsList" />


            </div>


        </div>
    </div>
</template>

<style scoped lang="scss"></style>