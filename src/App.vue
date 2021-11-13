<template>
  <h1>{{title}}</h1>
  <p v-show="isVisible">{{description}}</p>
  <p v-if="!isVisible">Mensaje oculto</p>
  <p v-else>Mensaje no oculto</p>
  <Todo></Todo>
</template>

<script>

import Todo from "@/components/Todo";
// import {ref, onMounted, onBeforeMount} from "vue";
export default {
  name: 'App',
  components: {Todo},
  // setup() {
  //   //propiedades reactivas
  //   const title = ref();
  //   const description = ref("Este es un mensaje de prueba.");
  //   const isVisible = ref(false);
  //
  //   //métodos del ciclo de vida (hooks)
  //   onMounted(() => {
  //     title.value = "Hola Richard";
  //   });
  //   onBeforeMount(() => {
  //     alert("Componente desmontado")
  //   })
  //
  //   return {
  //     title, description, isVisible
  //   }
  // },
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
</style>
