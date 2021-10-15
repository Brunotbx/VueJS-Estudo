<template lang="">
    <div>
        <h2>Hierarquia de componentes</h2>
        <form action="" @submit.prevent="enviarForm($event)">
         <div>
             <input type="text" v-model="name">
         </div>
         <br>
         <div>
             <input type="text" v-model="email">
         </div>
         <br>
        <Submit/>
    </form>
    </div>
</template>

<script>
import InputText from './forms/inputText.vue'
import Submit from './forms/Submit.vue'

export default {
    name: 'Form',
    components: {
        InputText,
        Submit
    },
    data() {
        return {
            name: "Bruno",
            email: "bruno@mktouch.com.br"
        }
    },
    methods: {
        enviarForm(e) {
            const name = this.name
            const email = this.email

            console.log(name, email)
        }
    },
}
</script>