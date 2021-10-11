<template lang="Vue">
     <PrimeiroComponente/>   <!--Declaração do componente que será renderizado -->
     <hr>
     <LifeCycles/>
     <hr>
     <Pessoa/>
     <hr>
     <Form/>
     <hr>
</template>

<script>
/* LOCAL PARA IMPORTAR COMPONENTES */
import PrimeiroComponente from './components/PrimeiroComponente.vue';
import LifeCycles from './components/LifeCycles.vue';
import Pessoa from './components/Pessoa.vue';
import Form from './components/Form.vue';

export default {
    name: 'App',    /* nome DESTE componente */

    components: {   /* Local para declaração dos componentes */
        PrimeiroComponente,
        LifeCycles,
        Pessoa,
        Form
    }
}
</script>

<style>

</style>