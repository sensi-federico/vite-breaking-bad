<script>
import { store } from '../store.js'

export default {
    name: 'AppBanner',
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h4 class="text-white bg-dark mt-2 p-3">Found {{ store.charsLength }} characters</h4>
</template>

<style>

</style>