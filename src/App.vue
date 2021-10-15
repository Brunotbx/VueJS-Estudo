<template lang="Vue">
        <Header/>
     <PrimeiroComponente/>   <!--Declaração do componente que será renderizado -->
     <hr>
     <LifeCycles/>
     <hr>
     <Pessoa/>
     <hr>
     <Form/>
     <hr>
     <p>LAST - 17</p>
</template>

<script>
/* LOCAL PARA IMPORTAR COMPONENTES */
import Header from './components/Header.vue';
import PrimeiroComponente from './components/PrimeiroComponente.vue';
import LifeCycles from './components/LifeCycles.vue';
import Pessoa from './components/Pessoa.vue';
import Form from './components/Form.vue';

export default {
    name: 'App',    /* nome DESTE componente */

    components: {   /* Local para declaração dos componentes */
        Header,
        PrimeiroComponente,
        LifeCycles,
        Pessoa,
        Form
    }
}
</script>

<style>
    body {
        background-color: rgb(231, 231, 231);
    }
    a {
        color: red;
    }
</style>