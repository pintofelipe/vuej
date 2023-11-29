<script setup>
import { ref } from 'vue';

import TaskComponent from '@/components/TaskComponent.vue'


let task = ref(['Estudiar para algebra','Descansar','Sacar 5.0','ir a natación','Estudiar fracciones parciales'])

let deleteTask = (index) => task.value.splice(index,1)


</script>

<template>

<div class=" bg-gray-200 w-96 shadow-md rounded mx-auto px-4 py-2 mt-12">
  <h1 class="text-6xl text-center font-semibold" >
    Coco77
  </h1>
<div class="flex mt-2">
  <input class="outline-none border-purple-900 rounded-r-none rounded bg-purple-200 w-4/5 border py-1 px-2 h-8" placeholder="Escribe su tarea">

  <span class=" transition-colors duration-300 hover:bg-purple-950 hover:cursor-pointer rounded-l-none rounded w-1/5 h-8 bg-purple-800 text-lg text-center font-bold text-white">+</span>
</div>

<TaskComponent
v-for="(tarea,index) in task" 
:key="index"
:tarea = "tarea"
:index = "index"
@borrarTarea = "deleteTask"
/>

</div>


</template>
