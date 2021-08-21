<template>
  <div id="Padre">
    <form id="tareas">
      <h2>Crar una nueva tarea</h2>
      <label>Tarea</label>
      <input
        type="text"
        v-model="nuevaTarea"
        placeholder="Ingresa una nueva tarea"
      />
      <button @click.prevent="agregarNuevaTarea">Crear</button>
    </form>
    <Hijo :tareas="this.tareas" @eliminar-tarea="eliminarTaeraLista"></Hijo>
  </div>
</template>

<script>
import Hijo from "./Hijo.vue";

export default {
  name: "Padre",
  data: () => ({
    nuevaTarea: "",
    tareas: []
  }),
  components: {
    Hijo
  },
  methods: {
    agregarNuevaTarea() {
      this.tareas.push(this.nuevaTarea);
      this.nuevaTarea = "";
    },
    eliminarTaeraLista(index) {
      this.tareas.splice(index, 1)
    }
  }
};
</script>

<style scoped></style>
