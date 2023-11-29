<script setup>
import TaskComponent from '@/components/TaskComponent.vue'
import { ref } from 'vue';

const taks = ref(['Estudiar', 'Sacar 5','Descansar'])

let deleteTask = (index) => taks.value.splice(index,1);

</script>

<template>
  <div class="bg-gray-50 w-96 px-4 py-3 shadow-md rounded mx-auto mt-12">
    <h1 class="text-center text-2xl font-semibold">Tareas</h1>

    
    <div class="flex mt-1">
      <input class="w-4/5 focus:outline-none focus:border-purple-500  rounded-r-none w-4/4 h-8 px-2 border rounded border-purple-700" type="">
      <span class="hover:cursor-pointer hover:bg-purple-950 rounded-l-none w-1/5 h-8 bg-purple-600 text-xl rounded text-center text-white">+</span>
    </div>
    
    <TaskComponent
    v-for="(tak,index) in taks"
     :key="index"
     :tarea = "tak"
     :index = "index" 
     @borrarTarea = "deleteTask"
    
    />




    
  </div>
</template>

<style scoped>

</style>
