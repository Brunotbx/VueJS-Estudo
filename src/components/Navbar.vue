<template>  
    <div id="nav">
        <router-link to="/" id="logo-url">
            <img 
                id="logo" 
                :src="logo" 
                :alt="alt"
            >
        </router-link>
        <router-link to="/">Home</router-link>
        <router-link to="/pedidos">Pedidos</router-link>
    </div>
</template>

<script>
export default {
    name: "Navbar",
    props: ["logo", "alt"]
}
</script>

<style scoped>
    #nav {
        background-color: #222;
        padding: 15px 50px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }
    #nav #logo-url{
        margin: auto;
        margin-left: 0;
    }
    #logo {
        width: 40px;
    }
    #nav a {
        color: #fcba03;
        text-decoration: none;
        margin: 10px;
        transition: 1s;
    }
    #nav a:hover {
        color: #fff;
        transform: scale(1.03,1.03);
    }
</style>