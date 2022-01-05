<template>
  <div>
    <Message :msg="msg" :visible="visible" />

    <form id="burger-form" method="POST" @submit="createBurger">
      <div class="input-container">
        <label for="name">Nome do cliente: </label>
        <input
          type="text"
          id="name"
          name="name"
          v-model="nome"
          placeholder="Digite o nome do cliente"
        />
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
        <label id="options-title" for="opcionais"
          >Escolha os adicionais:
        </label>
        <div
          class="checkbox-container"
          v-for="opcional in opcionaisData"
          :key="opcional.id"
        >
          <input
            type="checkbox"
            name="opcionais"
            v-model="opcionais"
            :value="opcional.tipo"
          />
          <span>{{ opcional.tipo }}</span>
        </div>
      </div>
      <div class="input-container">
        <input type="submit" class="submit-btn" value="Confirmar o pedido !" />
      </div>
    </form>
  </div>
</template>

<script>
import Message from "./Message.vue";

export default {
  name: "BurgerForm",

  components: {
    Message,
  },

  data() {
    return {
      visible: false,
      paes: null,
      carnes: null,
      opcionaisData: null,
      nome: null,
      pao: null,
      carne: null,
      opcionais: [],
      status: "Solicitado",
      msg: null,
    };
  },

  methods: {
    async getIngredientes() {
      const req = await fetch("http://localhost:3000/ingredientes");
      const data = await req.json();

      this.paes = data.paes;
      this.carnes = data.carnes;
      this.opcionaisData = data.opcionais;
    },

    async createBurger(event) {
      event.preventDefault();

      const data = {
        name: this.nome,
        carne: this.carne,
        pao: this.pao,
        opcionais: Array.from(this.opcionais),
        status: "Solicitado",
      };
      const dataJson = JSON.stringify(data);

      const req = await fetch("http://localhost:3000/burgers", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: dataJson,
      });

      const res = await req.json();

      this.visible = true
      this.msg = `Pedido N° ${res.id} realizado com sucesso!`;

      //Clean Message
      setTimeout(() => (this.visible = false, this.msg = ""), 6000);

      //Clean log
      this.nome = "";
      (this.pao = ""), (this.carne = ""), (this.opcionais = []);
    },
  },

  mounted() {
    this.getIngredientes();
  },
};
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

input,
select {
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
