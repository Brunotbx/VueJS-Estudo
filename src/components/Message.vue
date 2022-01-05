<template>
  <div class="message-container" v-if="visible">
      <p>{{ msg }}</p>
  </div>
</template>

<script>
export default {
    name: "Message",
    props: {
        msg: String,
        visible: Boolean
    }
}
</script>

<style>
    .message-container{
        position: fixed;
        z-index: 100;
        background-color: #a6fbc7;
        border: 2px solid #249c52;
        border-radius: 5px;
        padding: 30px;
        max-width: 400px;
        top: 20px;
        right: -300px;
        animation-name: animacao;
        animation-duration: 6s;
    }

    @keyframes animacao {
    0% {
        right: -300px;
    }
    25% {
        right: 25px;
    }
    50% {
        right: 25px;
    }
    75% {
        right: 25px;
    }
    100% {
        right: -300px;
    }
}
</style>