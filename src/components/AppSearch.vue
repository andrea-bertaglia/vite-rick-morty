<script>
import { store } from "../store"
export default {
    data() {
        return {
            store,
            statusArray: ["All", "Alive", "Dead", "Unknown"]
        }
    }
}
</script>

<template>
    <div class="container py-4">
        <div class="row text-center">
            <div>
                <span class="px-2">Seleziona lo status</span>
                <select @change="$emit('filter')" v-model="store.selectedStatus">
                    <option :value="status" v-for="status in statusArray">
                        {{ status }}</option>
                </select>
            </div>
            <div>
                <!-- <p>Trovati {{ store.CardsList.length }} elementi</p> -->
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss"></style>