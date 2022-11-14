<script>
import AppBanner from './AppBanner.vue'
import CharacterItem from './CharacterItem.vue'
import LoadingPage from './LoadingPage.vue'
import { store } from '../store.js'

export default {
    name: 'AppMain',
    components: {
        AppBanner,
        CharacterItem,
        LoadingPage
    },
    data() {
        return {
            store
        }
    }
}

</script>

<template>

    <div class="container bg-light">
        <div class="container p-2">
            <AppBanner />
        </div>
        <div class="my-container">
            <div class="row row-cols-5">
                <CharacterItem :character="character" v-for="character in store.characters"
                    v-if=" store.charsLength == 62" />
                <LoadingPage v-else />
            </div>
        </div>
    </div>

</template>

<style>

</style>