<template lang="">
    <div>
        <h2>Este componente descreve o usuário: {{ nome }}</h2>
        <Info/>
    </div>
</template>

<script>
/* LOCAL PARA IMPORTAR COMPONENTES */
import Info from './Info.vue'

export default {
    name: "Pessoa", /* Nome do componente para import em outros componentes */

    components: { /* Local para declaração dos componentes */
        Info
    },

    data() {
        return {
            nome: "Bruno"
        }
    },
}
</script>
