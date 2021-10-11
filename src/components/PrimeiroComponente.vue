<template lang="">
    <div>
        <h1>Material de estudos em VueJS 3</h1>
        <hr>
        <h2>Meu nome é: {{ nome }} e sou um {{ ocupacao }}.</h2>
    </div>
</template>

<script>
export default {
    name: 'PrimeiroComponente', //Nome do componente para exportação

    data() { // O campo dara irá guardar os dados do componente!
        return {
            nome: "Bruno",
            ocupacao: "Programador"
        }
    }
}
</script>
