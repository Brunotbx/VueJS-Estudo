<template lang="">
    <div>
        <h2>Hierarquia de componentes</h2>
        <form action="">
        <InputText value="1"/>
        <br><br>
        <InputText value="2"/>
        <br><br>
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
    }
}
</script>