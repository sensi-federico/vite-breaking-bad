<script>
export default {
    name: 'LoadingPage'
}
</script>

<template>

    <div class="center">
        <div class="ring"></div>
        <span>Loading...</span>
    </div>

</template>

<style lang="scss">
.center {
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;

    .ring {
        position: relative;
        left: 31rem;
        width: 100px;
        height: 100px;
        border-radius: 50%;
        margin: 2rem 0;
        animation: ring 2s linear infinite;

        @keyframes ring {

            0% {
                transform: rotate(0deg);
                box-shadow: 1px 3px 2px #e65c00;
            }

            50% {
                transform: rotate(180deg);
                box-shadow: 1px 3px 2px #18b201;
            }

            100% {
                transform: rotate(360deg);
                box-shadow: 1px 3px 2px #0456c8;
            }


        }

        &:before {
            content: '';
            position: relative;
            left: 31rem;
            top: 0;
            height: 100%;
            width: 100%;
            border-radius: 50%;
            box-shadow: 0 0 3px rgba($color: black, $alpha: .3);
        }
    }

    span {
        color: #737373;
        font-size: 15px;
        text-transform: uppercase;
        letter-spacing: 1px;
        line-height: 200px;
        position: relative;
        left: 25.2rem;
    }

}
</style>