<template>
  <div id="Hijo">
    <h2>Lista</h2>
    <ul>
      <li v-for="(tarea, index) in tareas" :key="index">
        {{ tarea }}
        <button @click="eliminarTarea(index)">Eliminar</button>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "Hijo",
  props: {
    tareas: Array
  },
  methods: {
    eliminarTarea(index) {
      this.$emit("eliminar-tarea", index)
    }
  }
};
</script>
<style scoped></style>
