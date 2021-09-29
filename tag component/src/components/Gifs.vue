<template>
    <div class="gifs">
        <img :src="gifs[indice].file" width="150"/>
        <span>
            <button @click="numero--">&lt;</button>
            <button @click="numero++">&gt;</button>
        </span>
    </div>
</template>

<script>

export default {
    data() {
        return {
            numero: 0,
            gifs: [{
                file: 'https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif',
            },
            {
                file: 'https://media.giphy.com/media/3oKIPnAiaMCws8nOsE/giphy.gif',
            },
            {
                file: 'https://media.giphy.com/media/iJCo9daAP0xugHhhfb/giphy.gif',
            }]
        }
    },
    computed: {
        indice() {
            return Math.abs(this.numero % 3)
        }
    }
}
</script>

<style scoped>
    .gifs {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    img {
        height: 200px;
        width: 200px;
    }
</style>
