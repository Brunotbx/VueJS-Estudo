<template>
    <div>
        <p> via Props - {{email}}</p>

        <p v-if="working">Trabalha atualmente.</p>
        <p v-else> Não está trabalhando.</p>
        <p>Utiliza as seguintes stacks : </p>
        <ul>
            <li>HTML</li>
            <li>CSS</li>
            <li>VUEJS</li>
        </ul>
        <div>
            <button @click="showEmail">{{buttonText}}</button>
        </div>
        <p v-show="show">E-mail para contato: <strong>{{ email }}</strong></p>
        <p>Link externo : <a v-bind:href="link" target="_blank">link</a></p>
        <Picture/>
    </div>
</template>

<script>
import Picture from './Picture.vue';

export default {
    name: 'Info',
    components: {
        Picture
    },
    props: {
        email: String,
        working: Boolean
    },
    data() {
        return {
            trabalhando: true,
            show: false,
            link: 'https://github.com/Brunotbx',
            buttonText: "Mostrar contato"
        }
    },
    methods: {
        showEmail () {
            this.show = !this.show
            if(!this.show){
                this.buttonText = "Mostrar contato"
            } else {
                this.buttonText = "Esconder contato"
            }
        }
    },
}
</script>
