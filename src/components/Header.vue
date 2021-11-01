<template>
    <ul>
        <li>
            <a href="#">Home</a>
        </li>
        <li>
            <a href="#">Projetos</a>
        </li>
        <li>
            <a href="#">Contato</a>
        </li>
        <li v-if="esta_logado">
            <a href="#">Meu Perfil</a>
        </li>
        
    </ul>
</template>

<script>
export default {
    name: 'Header',
    props: [
        "esta_logado"
    ]
}
</script>

<style scoped>
    ul {
        display: flex;
        list-style: none;
        background: #999;
    }

    li {
        margin-right: 10px;
    }

    a {
        color: #222;
        text-decoration: none;
        transition: .5s;
    }

    a:hover {
        color: blueviolet;
    }
</style>