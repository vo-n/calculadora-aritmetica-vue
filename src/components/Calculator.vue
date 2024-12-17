<script setup>
  import { reactive } from 'vue';

  const estado = reactive({
    value1: '',
    value2: '',
    operadodores: {
      somar: (a, b) => a + b,
      subtrair: (a, b) => a - b,
      multiplicar: (a, b) => a * b,
      dividir: (a, b) => (b !== 0 ? a / b : 'Não é possível realizar a divisão com o número 0.'),
    },
    resultado: '',
  })

  const calcular = () => {
    const { value1, value2, operacoes } = estado;
    estado.resultado = estado.operadodores[operacoes](parseFloat(value1), parseFloat(value2));
  }
</script>

<template>
  <div class="text-center">
    <h2>Sobre</h2>
    <p>Este é um projeto para o exercício do módulo 27 do curso de Desenvolvedor Full Stack Python da EBAC. O projeto
      consiste em crirar uma aplicação onde dois números inseridos nos campos sejam calculados conforme operação
      selecionada, sem que haja necessidade de um botão para a realização do cálculo.</p>
  </div>
  <form>
    <input v-model="estado.value1" @input="calcular" type="text" class="form-control text-center mb-1" required>
    <select v-model="estado.operacoes" @change="calcular" class="form-control text-center mb-1">
      <option value="somar">+</option>
      <option value="subtrair">-</option>
      <option value="multiplicar">*</option>
      <option value="dividir">/</option>
    </select>
    <input v-model="estado.value2" @input="calcular" type="text" class="form-control text-center" required>
  </form>
  <div class="pt-2">
    <span>Resultado: {{ estado.resultado }}</span>
  </div>
  
</template>

<style scoped>
  input::-webkit-outer-spin-button,
  input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }
</style>