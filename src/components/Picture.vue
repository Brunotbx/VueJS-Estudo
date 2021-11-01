<template>
    <img :src="avatar" :alt="descricao">
    <mudar-imagem @mudar-imagem="trocarImagem"/>
</template>

<script>
import MudarImagem from './MudarImagem.vue'

export default {
    name: 'Picture',
    components: {
        MudarImagem
    },
    data() {
        MudarImagem
        return {
            avatar: '/img/logo.png',
            descricao: 'logotipo'
        }
    },
    methods: {
        trocarImagem() {
            this.avatar = "/img/lobo.jpg";
        }
    }
}
</script>
