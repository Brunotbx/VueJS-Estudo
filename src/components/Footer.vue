<template>
    <footer id="footer">
        <p>
            Make your burger - Desenvoldido por Bruno &copy; 2021
        </p>
    </footer>
</template>

<script>
export default {
    name: "Footer"
}
</script>

<style scoped>
    #footer{
        height: 200px;
        width: 100%;
        background-color: #222;
        color: #fcba03;
        border-top: 4px solid #111;
        display: flex;
        justify-content: center;
        align-items: center;
        /*position: fixed;
        bottom: 0;*/
    }
</style>