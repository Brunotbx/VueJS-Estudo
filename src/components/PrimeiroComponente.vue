<template>
    <div>
        <h1>Material de estudos em VueJS 3</h1>
        <hr>
        <h2>Meu nome é: {{ nome }} e sou um {{ ocupacao }}.</h2>
        <hr>
        <MultiplosEventos/>
        <Reutilizacao/>
        <Reutilizacao/>
        <Reutilizacao/>
    </div>
</template>

<script>
import MultiplosEventos from './MultiplosEventos.vue'
import Reutilizacao from './Reutilizacao.vue'

export default {
    name: 'PrimeiroComponente', //Nome do componente para exportação

    components: {
        MultiplosEventos,
        Reutilizacao
    },

    data() { // O campo dara irá guardar os dados do componente!
        return {
            nome: "Bruno",
            ocupacao: "Programador"
        }
    }
}
</script>
