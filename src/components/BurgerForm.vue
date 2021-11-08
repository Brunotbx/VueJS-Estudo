<template>
    <div>
        <p>Mensagem</p>
        
        <form id="burger-form">
            <div class="input-container">
                <label for="name">Nome do cliente: </label>
                <input type="text" id="name" v-model="name" placeholder="Digite o nome do cliente">
            </div>

            <div class="input-container">
                <label for="bread">Tipo de pão: </label>
                <select name="pao" id="pao" v-model="pao" required>
                    <option value="">Escolha o tipo de pão</option>
                    <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">
                        {{ pao.tipo }}
                    </option>
                </select>
            </div>

            <div class="input-container">
                <label for="carne">Escolha o tipo de carne: </label>
                <select name="carne" id="carne" v-model="carne" required>
                    <option value="">Escolha a carne</option>
                    <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">
                        {{ carne.tipo }}
                    </option>
                </select>
            </div>

            <div id="options-container" class="input-container">
                <label id="options-title" for="opcionais">Escolha os adicionais: </label>
                <div class="checkbox-container" v-for="opcional in opcionaisdata" :key="opcional.id">
                    <input type="checkbox" name="opcionais" v-model="opicionais" :value="opcional.tipo">
                    <span>{{ opcional.tipo }}</span>
                </div>
            </div>
            <div class="input-container">
                <input type="submit" class="submit-btn" value="Confirmar o pedido !">
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: "BurgerForm",
    data() {
        return {
            paes:null,
            carnes: null,
            opcionaisdata: null,
            name: null,
            pao: null,
            carne: null,
            opicionais: [],
            status: "Pedido confirmado",
            msg: null
        }
    },

    methods: {
        async getIngredientes() {
            const req = await fetch('https://jsonkeeper.com/b/TBU4');
            const data = await req.json();

            this.paes = data.ingredientes.paes;
            this.carnes = data.ingredientes.carnes;
            this.opcionaisdata = data.ingredientes.opcionais
        }
    },

    mounted() {
        this.getIngredientes();
    }
}
</script>

<style scoped>
    #burger-form {
        max-width: 400px;
        margin: 0 auto;
    }

    .input-container {
        display: flex;
        flex-direction: column;
        margin-bottom: 10px;
    }

    label {
        font-weight: bold;
        margin-bottom: 15px;
        padding: 5px 10px;
        color: #222;
        border-left: 4px solid #fcba03;
    }

    input, select {
        padding: 5px 10px;
        width: 300px;
    }

    #options-container {
        flex-direction: row;
        flex-wrap: wrap;
    }

    #options-title {
        width: 100%;
    }

    .checkbox-container {
        display: flex;
        align-items: center;
        width: 50%;
    }

    .checkbox-container span,
    .checkbox-container input {
        width: auto;
    }

    .checkbox-container span {
        margin-left: 5px;
        font-weight: bold;
    }

    .submit-btn {
        background-color: #222;
        color: #fcba03;
        font-weight: bold;
        font-size: 16px;
        padding: 10px;
        border: 2px solid #222;
        border-radius: 5px;
        cursor: pointer;
        transition: 1s;
    }

    .submit-btn:hover {
        background-color: transparent;
        color: #222;
    }
</style>