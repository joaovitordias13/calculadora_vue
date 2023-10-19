<script >
  export default{
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao:'soma',
    }
  },
  computed: {
    resultado() {
      switch(this.operacao){
        case 'soma':
          return this.numero1 + this.numero2;
        case 'subtracao':
          return this.numero1 - this.numero2;  
        case 'multiplicacao':
          return this.numero1 * this.numero2; 
        case 'divisao':
          return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'infinito';
          default:
          return 0;   
      }
    },
  },
}
</script>

<template>
  <div id="container">
      <h1>Calculadora Vue</h1>
  <div>
    <label for="numero1">Primeiro número:</label>
    <input v-model.number="numero1" @input="calcular">
  </div>
  <div class="operacao">
    <label for="operacao">Operações:</label>
    <select v-model="operacao" @change="calcular">
      <option value="soma">+</option>
      <option value="subtracao">-</option>
      <option value="multiplicacao">*</option>
      <option value="divisao">/</option>
    </select>
  </div>
  <div>
    <label for="numero2">Segundo número:</label>
    <input v-model.number="numero2" @input="calcular">
  </div>
  <div>
    <h2>Resultado: {{ resultado }}</h2>
  </div>
</div>
</template>

<style>
  #container{
    font-family: Arial, sans-serif;
    text-align: center;
    padding-bottom: 20px;
    color: #2c3e50;
  }
  .operacao{
    margin: 20px;
  }
</style>
