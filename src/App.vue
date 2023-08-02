<script setup>
import { reactive } from 'vue';
import Heade from './components/head.vue';
import Dados from './components/dados.vue';
import Resultado from './components/result.vue';

const estado = reactive({
  filtro: 'soma',
  numb1: '',
  numb2: '',
  resultado: '',
})

const soma = () => {
  const resultadoSoma = estado.numb1 + estado.numb2
  estado.resultado = resultadoSoma;
  return estado.resultado
}

const subtracao = () => {
  const resultadoSubtracao = estado.numb1 - estado.numb2
  estado.resultado = resultadoSubtracao;
  return estado.resultado
}

const multiplicacao = () => {
  const resultadoMultiplicacao = estado.numb1 * estado.numb2
  estado.resultado = resultadoMultiplicacao;
  return estado.resultado
}

const divisao = () => {
  const resultadoDivisao = estado.numb1 / estado.numb2
  estado.resultado = resultadoDivisao
  return estado.resultado
}
</script>

<template>
  <div class="container">
    <Heade />
    <div class="calculadora">
      
      <Dados :valorPrimeiroInput="evente => estado.numb1 = Number(evente.target.value)" :valorSegundoInput="evente => estado.numb2 = Number(evente.target.value)" :filtro="estado.filtro" :selecionaFiltro=" evente => estado.filtro = evente.target.value"/>
      
      </div>
      <Resultado :filtro="estado.filtro" :funcaoSoma="soma()" :funcaoSub="subtracao()" :funcaoMult="multiplicacao()" :funcaoDivisao="divisao()" />
  </div>
</template>

<style scoped>
.container {
 
  width: 2300px;

 margin: 0 auto;
}

@media screen and (min-width: 360px) {
  .container {
    width: 90%;
  }
 
}
</style>