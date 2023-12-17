<template>
  <div>
    <label for="numero1">Número 1:</label>
    <input v-model="numero1" type="number" @input="calcularResultado">

    <label for="operacao">Operação:</label>
    <select v-model="operacao" @change="calcularResultado">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>

    <label for="numero2">Número 2:</label>
    <input v-model="numero2" type="number" @input="calcularResultado">

    <label for="resultado">Resultado:</label>
    <input :value="resultado" type="text" readonly>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
      resultado: 0
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case '+':
          this.resultado = this.numero1 + this.numero2;
          break;
        case '-':
          this.resultado = this.numero1 - this.numero2;
          break;
        case '*':
          this.resultado = this.numero1 * this.numero2;
          break;
        case '/':
          this.resultado = this.numero1 / this.numero2;
          break;
      }
    }
  }
}
</script>

