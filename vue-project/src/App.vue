<template>
  <div class="container">
    <h2>Calculadora Aritmética</h2>
    <div class="inputs">
      <input type="number" v-model="num1" placeholder="Número 1" />
      <select v-model="operacao">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
      </select>
      <input type="number" v-model="num2" placeholder="Número 2" />
    </div>
    <h3>Resultado: {{ resultado }}</h3>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operacao: "+",
    };
  },
  computed: {
    resultado() {
      const n1 = parseFloat(this.num1);
      const n2 = parseFloat(this.num2);
      switch (this.operacao) {
        case "+": return n1 + n2;
        case "-": return n1 - n2;
        case "*": return n1 * n2;
        case "/": return n2 !== 0 ? n1 / n2 : "Erro (divisão por zero)";
        default: return 0;
      }
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 300px;
  margin: auto;
  text-align: center;
  font-family: Arial, sans-serif;
}
.inputs {
  display: flex;
  gap: 5px;
  justify-content: center;
  margin-bottom: 10px;
}
input, select {
  padding: 5px;
  font-size: 16px;
}
</style>
