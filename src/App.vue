<script setup>
import { reactive } from 'vue';
import Formulario from './components/Formulario.vue';

const estado =reactive ({
  valor_x : null,
  valor_y : null,
  resultado: 0 ,
  tipoOperacao : '',
 
})

const executarOperacao = (operacao, x, y) => {
    x = parseFloat(estado.valor_x);
    y = parseFloat(estado.valor_y);
    operacao = estado.tipoOperacao;
 
    switch (operacao){
      case '+': return ( estado.resultado = x + y);
      case '-': return ( estado.resultado = x - y);
      case '*': return ( estado.resultado = x * y);
      case '/': return ( estado.resultado = x / y);
    }
}



</script>

<template>

 <div class = "container card mt-5 ">
  <Formulario :selecionar-operacao = "evento => estado.tipoOperacao = evento.target.value"
              :valor-x ="evento => estado.valor_x = evento.target.value"
              :valor-y ="evento => estado.valor_y = evento.target.value" 
              :executar-operacao="executarOperacao()"
              :resultado = "estado.resultado"
              
              />
       
    </div>

</template>

<style scoped>

</style>
