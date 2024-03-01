<script setup>
  const nome = 'Ruama'
  const nome2 = 'Vitória'
    const idade = 16;

    function inverter(texto) {
        return texto.split('').reverse().join('')
    }

    function saudacao() {
        return `Olá, ${nome} e ${nome2}!`
    }

  import { ref } from "vue";

  const contador = ref(0)

  function incrementar() {
    contador.value++;
  }

  function decrementar() {
    if (contador.value > 0) contador.value--
  }

  function recomeçar() {
    contador.value = 0
  }
</script>

<template>

  <div class="fundo">
    <div class="info">
          <h1>Informações dos alunos</h1>
          <p>Nomes: {{ nome }} e {{ nome2 }}. </p>
          <p>Idades: {{ idade }}  anos.</p>
          
          <p>Para completar 50 anos faltam: {{ 50 - idade }}  anos.</p>
          <p>O nome Ruama tem {{ nome.length }}  caracteres.</p>
          <p>O nome Vitória tem {{ nome2.length }}  caracteres.</p>
          <p>O nome Ruama invertido é: {{ inverter(nome) }}.</p>
          <p>O nome Vitória invertido é: {{ inverter(nome2) }}.</p>
          <p> Exemplo de saudação usando função:</p>
          <p> {{ saudacao() }}  </p>
    </div>

    <div class="info">
      <h1>Contador</h1>
      <button @click="incrementar" >+</button>
      <button @click="decrementar">-</button>
      <button @click="recomeçar">recomeçar</button>
      <p class="p">Valor do Contador: {{ contador }}</p>

      <div class="p" :style="{ backgroundColor: contador > 9 ? 'purple' : '#f5c951'}">
      <p v-if="contador > 9">Valor maior que 10</p>
      <p v-else>Valor menor que 10</p>
    </div>
    </div>

  </div>

</template>

<style scoped>
.info {
  background-color: rgb(190, 25, 97);
  padding: 20px 30px;
  color: rgb(240, 226, 237);
  border-radius: 10px;
}

h1 {
  color: white;
  font-weight: bold;
  font-size: 1.5em;
}

.fundo {
  display: grid;
  row-gap: 1rem;
    background-color: rgb(224, 113, 161);
    padding: 15px 20px;
    color: rgb(183, 210, 219);
    border-radius: 10px;
  }


  button {
    margin: 8px;
    padding: 8px 45px;
    border: 0;
    border-radius: 5px;
    background-color: rgb(224, 113, 161);
    color: white;
    font-weight: bold;
    cursor: pointer;
  }

 .p {
  border-radius: 5px;
  padding: 3px 10px;
 }
</style>
