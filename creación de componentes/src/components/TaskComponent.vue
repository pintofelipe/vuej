<script setup>
const props = defineProps({
  tarea: {
    type: String,
    default: 'tarea por defecto'
  },
  index: {
    type: Number
  }
})

let emit = defineEmits(['borrarHijo'])

let borrarTarea = (index) => {
  emit('borrarTarea', index)
}

</script>

<template>
  <div class="px-4 py-1 rounded mt-1 flex bg-purple-500 justify-between">
    {{ props.tarea }}
    <span
      @click="borrarTarea(props.index)"
      class="px-2 transition-colors duration-300 hover:bg-purple-950 hover:cursor-pointer rounded bg-purple-800 text-center text-white"
      >X</span
    >
  </div>
</template>
