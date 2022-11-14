<script>
export default {
    name: 'CharacterItem',
    props: {
        character: Object
    }
}

</script>

<template>
    <div class="col">
        <div class="character">
            <img :src="character.image" :alt="character.name">
            <h3>{{ character.name }}</h3>
            <div class="series">{{ character.series }}</div>
            <div class="status">{{ character.status }}</div>
        </div>
    </div>
</template>

<style>

</style>