<script setup>
import { reactive } from "vue";

const values = reactive({
  firstNumber: 0,
  secondNumber: 0,
  operacao: "adicao",
  result: 0,
});

function calcular() {
  switch (values.operacao) {
    case "adicao":
      values.result = values.firstNumber + values.secondNumber;
      break;
    case "subtracao":
      values.result = values.firstNumber - values.secondNumber;
      break;
    case "multiplicacao":
      values.result = values.firstNumber * values.secondNumber;
      break;
    case "divisao":
      values.result = values.firstNumber / values.secondNumber;
      break;
  }
}

function handleInputChange(inputType, event) {
  const value = event.target.value === "" ? 0 : parseFloat(event.target.value);

  if (inputType === "firstNumber") {
    values.firstNumber = value;
  } else if (inputType === "secondNumber") {
    values.secondNumber = value;
  } else if (inputType === "operacao") {
    values.operacao = event.target.value;
  }
  calcular();
}
</script>

<template>
  <div class="container">
    <div class="text-center mt-5">
      <h1>Calculadora com Vue.js</h1>
    </div>
    <div class="d-flex flex-column mt-4 align-items-center gap-3">
      <input
        type="number"
        class="w-25 form-control"
        @input="(e) => handleInputChange('firstNumber', e)"
        placeholder="Digite um numero"
      />
      <input
        type="number"
        class="w-25 form-control"
        @input="(e) => handleInputChange('secondNumber', e)"
        placeholder="Digite um numero"
      />
      <select
        class="w-25 form-control"
        @change="(e) => handleInputChange('operacao', e)"
      >
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
      </select>
    </div>
    <div class="d-flex justify-content-center mt-4">
      <div class="text-center border border-dark rounded p-5">
        <h1>Resultado</h1>
        <h1 class="display-1">{{ values.result }}</h1>
      </div>
    </div>
  </div>
</template>

<style scoped></style>