<template>
  <ul>
    <li
        :class="{'bg-goldenrod': isDesktop}"
        :style="{color: aColor, fontSize: fontSize + 'px'}"
        v-for="task in tasks"
        :key="task.id"
    >
      {{task.task}}
    </li>
  </ul>
</template>

<script>
export default {
  name: "Todo",
  data() {
    return {
      tasks: [
        {
          id: 1,
          task: "Crear curso 1",
          isCompleted: false
        },
        {
          id: 2,
          task: "Crear curso 2",
          isCompleted: false
        },
        {
          id: 2,
          task: "Crear curso 3",
          isCompleted: false
        }
      ],
      isDesktop: true,
      aColor: "white",
      fontSize: 20,
    }
  }
}
</script>

<style scoped>

</style>