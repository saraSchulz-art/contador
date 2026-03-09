<script setup >
  import { ref } from 'vue';
  const contador = ref(0);
  const num = ref(5);

  function incrementar() {
    if (contador.value + num.value >= 10) {
      contador.value = 10;
    }else{
      contador.value = contador.value + num.value;
    }
  }

  function decrementar() {
    if (contador.value - num.value <= 0) {
      contador.value = 0;
    }else{
      contador.value = contador.value - num.value;
    }
  }
</script>

<template>
  <div class="container">
    <p>Valor do Contador: {{ contador }}</p>
    <p>Volor a encrementar/decrementar<input type="number" v-model="num" max="10" min="1"></p>
    <div>
      <button @click="incrementar" :disabled="contador >= 10">Incrementar</button>
      <button @click="decrementar" :disabled="contador <= 0">Decrementar</button>
    </div>
    <div v-if="contador === 10">
      <p>O contador está  no máximo</p>
    </div>
    <div v-if="contador === 0">
      <p>O contador esta no mínimo</p>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
}
</style>
