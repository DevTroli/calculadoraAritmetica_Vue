<script setup>
    const props = defineProps([resultado, num1, num2, operation])
    </script>

<template>
    <div class="row g-3 bg-light">
    <div class="col-sm-4">
      <input required class="form-control mb-3 " v-model.number="props.num1" type="number" placeholder="Digite um número" @keyup="calcularResultado">
    </div>
    <div class="col-sm-auto">
      <select class="form-select mb-3" v-model="props.operation" @change="calcularResultado">
        <option value="adição">+</option>
        <option value="Subtração">-</option>
        <option value="multiplicação">*</option>
        <option value="divisão">/</option>
      </select>
    </div>
    <div class="col-sm-4">
      <input required class="form-control mb-3 " v-model.number="props.num2" type="number" placeholder="Digite mais um número" @keyup="calcularResultado">
    </div>
    <div class="col-sm-auto">
        <h3>Resultado: {{ props.resultado }}</h3>
      </div>
  </div>
</template>