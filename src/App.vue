<script>
export default {
  data() {
    return {
      valorConta: 0,
      Gorjeta: 15,
      numPessoas: 1,
    };
  },
  methods: {
    calcular() {
      const valorConta = this.valorConta;
      const Gorjeta = this.Gorjeta;
      const numPessoas = this.numPessoas;
      let valorGorjeta = 0;
      let valorTotal = {};
      valorGorjeta = valorConta * (Gorjeta / 100);
      valorTotal = (valorConta + valorGorjeta) / numPessoas;
      valorTotal = Math.round(valorTotal * 100) / 100;
      valorTotal = valorTotal.toFixed(2);
      console.log(valorTotal);
      document.getElementById("resultado").innerHTML = valorTotal;
    },
  },
};
</script>

<template>
  <main>
    <div class="calculadora">
      <form>
        <h1>Calculadora de Gorjetas</h1>
        <label>
          <p>Valor do Serviço:</p>
          <input type="number" v-model="valorConta" id="valorConta" />
        </label>
        <label>
          <p>Qualidade do Serviço:</p>
          <select v-model="Gorjeta" id="valorGorjeta">
            <option value="30">30% (Excepcional)</option>
            <option value="25">25% (Mais do que bom)</option>
            <option value="20">20% (Bom)</option>
            <option value="15">15% (Ok)</option>
            <option value="10">10% (Ruim)</option>
            <option value="5">5% (Péssimo)</option>
          </select>
        </label>
        <label>
          <p>Quantas pessoas vão dividir a conta?</p>
          <input v-model="numPessoas" type="number" id="numPessoas" />
        </label>
        <label>
          <p>Valor para cada:</p>
          <button type="button" @click="calcular">
            R$:<span id="resultado">0.00</span>
          </button>
        </label>
      </form>
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  justify-content: center;
  background-color: rgb(236, 158, 158);
  border-radius: 10px;
}
.calculadora {
  text-align: center;
}

p{
  font-size: 1rem;
  font-weight: 500;
}
h1 {
  text-align: center;
  color: rgb(0, 0, 0);
  font-size: 2rem;
  
}

input,
select {
  width: 100%;
  margin-bottom: 30px;
}
.calculadora {
  padding: 10px;
  
}
input,
select,
button {
  padding: 10px;
  width: 250px;
  height: 25px;
  font-size: 18px;
  border: 1px black solid;
  border-radius: 5px;
  text-align: center;
  transition: 0.25s;
  cursor: pointer;
}
button {
  background-color: #7F1D1D;
  color: white;
  height: 50px;
  font-size: 24px;
  margin-bottom: 10px;
  border-radius: 30px;
}
</style>
