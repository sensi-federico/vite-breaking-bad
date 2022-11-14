<script>
export default {
    name: 'CharacterItem',
    props: {
        character: Object
    }
}

</script>

<template>
    <div class="col g-3">
        <div class="card bg-dark p-2">
            <img :src="character.img" :alt="character.name">
            <h5 class="text-white text-center pt-3">{{ character.name }}</h5>
            <div class="series text-muted">{{ character.category }}</div>
            <div class="status text-muted">{{ character.status }}</div>
        </div>
    </div>
</template>

<style lang="scss">
.card {

    height: 450px;

    img {
        width: 200px;
        height: 250px;
    }

    div {
        text-align: center;
        padding: .5rem;
    }
}
</style>