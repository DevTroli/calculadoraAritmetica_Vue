<script>
import { reactive } from 'vue'

export default {
  setup() {
    const estado = reactive({
      num1: 0,
      num2: 0,
      operation: 'adição',
      resultado: 0
    })

    const calcularResultado = () => {
      switch (estado.operation) {
        case 'adição':
          estado.resultado = estado.num1 + estado.num2;
          break;
        case 'Subtração':
          estado.resultado = estado.num1 - estado.num2;
          break;
        case 'multiplicação':
          estado.resultado = estado.num1 * estado.num2;
          break;
        case 'divisão':
          estado.resultado = estado.num1 / estado.num2;
          break;
        default:
          estado.resultado = 0;
      }
    }

    return { estado, calcularResultado }
  }
}
</script>

<template>
  <header class="p-5 mb-4 bg-dark rounded-3">
    <h1>Calculadora Aritmética</h1>
    <p>Realize operações matemáticas à vontade</p>
  </header>
  <div class="row g-3 bg-light">
    <div class="col-sm-4">
      <input required class="form-control mb-3 " v-model.number="estado.num1" type="number" placeholder="Digite um número"
        @keyup="calcularResultado">
    </div>
    <div class="col-sm-auto">
      <select class="form-select mb-3" v-model="estado.operation" @change="calcularResultado">
        <option value="adição">+</option>
        <option value="Subtração">-</option>
        <option value="multiplicação">*</option>
        <option value="divisão">/</option>
      </select>
    </div>
    <div class="col-sm-4">
      <input required class="form-control mb-3 " v-model.number="estado.num2" type="number"
        placeholder="Digite mais um número" @keyup="calcularResultado">
    </div>
    <div class="col-sm-auto">
      <h3>Resultado: {{ estado.resultado }}</h3>
    </div>
  </div>
</template>


<style>
#app {
  font-family:Helvetica, Arial, sans-serif;
  text-align: center;
  overflow-x: hidden;
}

header h1,
header p {
  color: #ffffff;
}</style>
