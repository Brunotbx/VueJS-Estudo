<template lang="">
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
    </ul>
</template>

<script>
export default {
    name: 'Header'
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