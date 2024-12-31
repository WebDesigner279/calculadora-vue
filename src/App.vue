<template>
  <div id="app" class="calculator">
    <h1>Calculadora Aritmética</h1>
    <div class="input-container">
      <input type="number" v-model.number="num1" placeholder="Digite o primeiro número" />
      <select v-model="operation">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model.number="num2" placeholder="Digite o segundo número" />
    </div>
    <div class="result">
      <h2>Resultado: {{ result }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operation: "+",
    };
  },
  computed: {
    result() {
      switch (this.operation) {
        case "+":
          return this.num1 + this.num2;
        case "-":
          return this.num1 - this.num2;
        case "*":
          return this.num1 * this.num2;
        case "/":
          return this.num2 !== 0 ? this.num1 / this.num2 : "Erro: Divisão por zero";
        default:
          return "Operação inválida";
      }
    },
  },
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 50px;
}
.input-container {
  margin: 20px;
  display: flex;
  gap: 10px;
  justify-content: center;
}
input, select {
  padding: 10px;
  font-size: 16px;
}
.result {
  margin-top: 20px;
  font-size: 24px;
  font-weight: bold;
}
</style>
