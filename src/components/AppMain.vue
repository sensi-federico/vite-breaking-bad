<script>
import AppBanner from './AppBanner.vue'
import CharacterItem from './CharacterItem.vue'
import LoadingPage from './LoadingPage.vue'
import CategorySelector from './CategorySelector.vue'
import axios from 'axios'
import { store } from '../store.js'

export default {
    name: 'AppMain',
    components: {
        AppBanner,
        CharacterItem,
        LoadingPage,
        CategorySelector
    },
    data() {
        return {
            store
        }
    },
    methods: {
        selector() {
            let categoryUrl = store.API_URL
            if (this.store.categorySelector !== 'all') {
                const series = this.store.categorySelector
                categoryUrl = `${this.store.API_URL}?category=${series}`
                console.log('sono qui dentro');
            }
            console.log('sono qui fuori');

            axios.get(categoryUrl)
                .then(response => {
                    console.log(response)
                    this.store.characters = response.data
                    this.store.charsLength = response.data.length
                })
                .catch(err => {
                    console.log(err.message);
                })
        }
    }
}

</script>

<template>

    <div class="container bg-light">
        <div class="container p-2">
            <AppBanner />
        </div>
        <div class="my-container p-2">
            <CategorySelector @selector='selector' />
            <div class="row row-cols-5">
                <CharacterItem :character="character" v-for="character in store.characters"
                    v-if="store.charsLength == 62 || store.charsLength == 12 || store.charsLength == 57" />
                <LoadingPage v-else />
            </div>
        </div>
    </div>

</template>

<style>

</style>