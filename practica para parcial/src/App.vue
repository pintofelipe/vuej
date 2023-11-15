<script setup>
import { ref, computed } from 'vue'

const felipe = ref('coco77')
const acumulador = ref(0)

const incrementar = () => acumulador.value++
const decrementar = () => acumulador.value--
const reset = () => (acumulador.value = 0)
const numberCliente = ref([]);




const classCounter = computed(() => {
  if (acumulador.value > 0) {
    return 'positive'
  }
  if (acumulador.value < 0) {
    return 'negative'
  }
  if (acumulador.value === 0) {
    return 'zero'
  }
})



const add = ()=>{
  numberCliente.value.push(acumulador.value);
}


const bloquearBtnAdd = computed(() =>{
  const numSearch = numberCliente.value.find(num =>{
    num === acumulador.value;
    if(numSearch === 0){
      return true;
    }
    return numSearch ? treu: false;
  })
})
</script>

<template>
  <h1>{{ felipe.toUpperCase() }}</h1>

  <h2 :class="classCounter">{{ acumulador }}</h2>

  <button @click="incrementar">incrementar</button>
  <button @click="decrementar">Decrementar</button>
  <button @click="reset">reset</button>
  <button @click="add">add</button>
  <br />
  <h2>{{ numberCliente }}</h2>
  <ul>
    <li v-for="(number,index) in numberCliente"
    :key="index">
      {{ number}}
    </li>
  </ul>

  
</template>

<style scoped>
.positive {
  color: green;
}

.negative {
  color: red;
}
.zero {
  color: peru;
}
</style>
