<script setup>
const props = defineProps({
  tarea: {
    typy: String,
    default: 'Tarea indefinida'
  },
  index: Number
})


let borrarTarea = (index) => emit('borrarTarea',index);

const emit = defineEmits(['borrarTarea'])




</script>

<template>
  <div class="flex justify-between py-1 mt-2 rounded px-4 bg-purple-400">
    {{ props.tarea }}
    <span
      class="px-2 h-8 hover:bg-purple-800 bg-purple-600 text-xl rounded text-center text-white hover:cursor-pointer"
      @click="borrarTarea(props.index)"
      >
      X
    </span>
  </div>
</template>

<style scoped></style>
