<template>
    <div id="main-banner">
        <h1>Make your Burger</h1>
    </div>
</template>

<script>
export default {
    name: "Banner"
}
</script>

<style scoped>
    #main-banner {
        background-image: url('/img/burger.jpg');
        background-position: bottom;
        background-size: cover;
        height: calc(100vh - 76px);
        display: flex;
        align-items: center;
        justify-content: left;
    }

    #main-banner h1{
        color: #fff;
        text-align: center;
        font-size: 60px;
        margin-left: 15px;
    }

   #main-banner h1::before{
        content: "";
        display: inline-block;
        width: 10px;
        height: 10px;
        background-color: #fcba03;
        margin-right: 5px;
        animation: blinker 1.5s linear infinite;
    }

    @keyframes blinker {
        50% {
        opacity: 0;
    }
    }

</style>