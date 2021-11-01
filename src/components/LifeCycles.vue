<template>
    <div>
        <h2>Life Cycle exemple: {{ informacao }}</h2>
    </div>
</template>

<script>
export default {
    name: "LifeCycles",
    
    data() {
        return {
            informacao: "Fase 1"
        }
    },

    created() { //Executa este bloco após criar o componente
        setTimeout(()=>{
            this.informacao = "Fase 2"
        },1500);
    },

    mounted() { //Executa este bloco após montar o componente em tela
        setTimeout(()=>{
            this.informacao = "Fase 3"
            this.lifeCycle();
        },2500);
    },
    methods: {
        lifeCycle(){
            console.log('Foi!')
        }
    },
}
</script>
