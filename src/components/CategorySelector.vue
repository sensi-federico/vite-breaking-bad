<script>
import { store } from '../store.js'

export default {
    name: 'CategorySelector',
    data() {
        return {
            store
        }
    }
}

</script>

<template>

    <div class="selector">
        <select class="form-select form-select-lg mb-3" v-model="store.categorySelector" @change="$emit('selector')">
            <option selected value="all">All</option>
            <option value="Breaking Bad">Breaking Bad</option>
            <option value="Better Call Saul">Better Call Saul</option>
        </select>
    </div>

</template>

<style lang="scss">
select {
    max-width: 200px;
}
</style>