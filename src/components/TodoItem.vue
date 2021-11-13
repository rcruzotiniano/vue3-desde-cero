<template>
  <li :class="{done: isCompleted, 'bg-goldenrod': isDesktop}">
    {{task}}
  </li>
</template>

<script>
export default {
  name: "TodoItem",
  props: {
    task: null,
    isCompleted: null,
    isDesktop: null,
  }
}
</script>

<style scoped>
  .done {
    color: white;
    background: cornflowerblue;
    font-size: 16px;
  }
</style>