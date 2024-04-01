<script>
export default {
  name: 'App',
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'adicao',
    };
  },
  methods: {
    atualizaNumero1(event) {
      this.numero1 = parseFloat(event.target.value) || 0;
    },
    atualizaNumero2(event) {
      this.numero2 = parseFloat(event.target.value) || 0;
    },
    atualizaOperacao(event) {
      this.operacao = event.target.value;
    },
    calcular() {
      switch (this.operacao) {
        case 'adicao':
          return this.numero1 + this.numero2;
        case 'subtracao':
          return this.numero1 - this.numero2;
        case 'multiplicacao':
          return this.numero1 * this.numero2;
        case 'divisao':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: Divisão por zero';
        default:
          return 0;
      }
    },
  },
};
</script>


<template>
 <div id="app">
    <h1>Calculadora Aritmética</h1>
    <div class="components">
      <input type="number" :value="numero1" @input="atualizaNumero1($event)" placeholder="Número 1">
    <input type="number" :value="numero2" @input="atualizaNumero2($event)" placeholder="Número 2">
    <select :value="operacao" @change="atualizaOperacao($event)">
      <option value="adicao">Adição</option>
      <option value="subtracao">Subtração</option>
      <option value="multiplicacao">Multiplicação</option>
      <option value="divisao">Divisão</option>
    </select>
    </div>
    <div class="result">Resultado: {{ calcular() }}</div>
  </div>
</template>

<style>
  #app {
  display: block;
  text-align: center;
  background-color: lightpink;
  color: lightcyan;

}
  .components {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    column-gap: 10%;
    margin: 5px;
    padding: 10px;
  }

</style>
