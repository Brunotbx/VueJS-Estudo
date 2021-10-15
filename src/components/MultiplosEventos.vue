<template lang="">
    <div>
        <button @click="primeiro('Primeiro Evento', $event), segundo('Segundo Evento', $event), terceiro()">Ativar multiplos eventos</button>
        <p>{{ multiplos_eventos }}</p>
    </div>
</template>

<script>
export default {

    name: 'MultiplosEventos',

    data() {
        return {
            multiplos_eventos: ""
        }
    },

    methods: {
        primeiro(txt, e) {
            this.multiplos_eventos = txt
        },
        segundo(txt, e) {
            setTimeout( () => this.multiplos_eventos = txt, 1000 );
        },
        terceiro() {
            setTimeout( () => this.multiplos_eventos = "", 2000 );
        }
    },
}
</script>

<style scoped>
    div {
        margin: 100px;
    }
</style>
    