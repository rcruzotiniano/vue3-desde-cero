<template>
  <h1>{{title}}</h1>
  <p v-show="isVisible">{{description}}</p>
  <p v-if="!isVisible">Mensaje oculto</p>
  <p v-else>Mensaje no oculto</p>
  <input v-model="description" type="text">
  <Todo></Todo>
</template>

<script>

import Todo from "@/components/Todo";
export default {
  name: 'App',
  components: {Todo},
  data() {
    return {
      title: "Hola Richard",
      description: "Este es un mensaje de prueba.",
      isVisible: false,
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.bg-goldenrod {
  background: goldenrod;
  margin: 1rem;
}
</style>
