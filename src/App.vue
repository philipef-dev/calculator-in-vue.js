<script setup>


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
        placeholder="Digite um numero"
      />
      <input
        type="number"
        class="w-25 form-control"
        placeholder="Digite um numero"
      />
      <select class="w-25 form-control">
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
      </select>
    </div>
    <div class="d-flex justify-content-center mt-4">

    </div>
  </div>
</template>

<style scoped></style>
