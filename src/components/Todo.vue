<template>
  <input v-model="newTask" type="text" @keyup.enter="addTask">
  <ul>
    <TodoItem
        v-for="task in tasks"
        :key="task.id"
        :task="task.task"
        :is-completed="task.isCompleted"
        :is-desktop="isDesktop"
    >
      {{task.task}}
    </TodoItem>
  </ul>
</template>

<script>
import {ref} from "vue";
import {v4 as uuidv4} from "uuid";
import TodoItem from "@/components/TodoItem";
export default {
  name: "Todo",
  components: {TodoItem},
  setup() {
    //Propiedades reactivas
    const tasks = ref(
        [
          {
            id: uuidv4(),
            task: "Crear curso 1",
            isCompleted: true
          },
          {
            id: uuidv4(),
            task: "Crear curso 2",
            isCompleted: false
          },
          {
            id: uuidv4(),
            task: "Crear curso 3",
            isCompleted: true
          }
        ]
    );
    const isDesktop = ref(true);
    const aColor = ref("white");
    const fontSize = ref(16);
    const newTask = ref();

    //Métodos
    const addTask = () => {
      tasks.value.push({
        id: uuidv4(),
        task: newTask.value,
        isCompleted: false
      })
      newTask.value = null;
    }

    return {
      tasks, isDesktop, aColor, fontSize, newTask, addTask
    }
  },
  // data() {
  //   return {
  //     tasks: [
  //       {
  //         id: uuidv4(),
  //         task: "Crear curso 1",
  //         isCompleted: false
  //       },
  //       {
  //         id: uuidv4(),
  //         task: "Crear curso 2",
  //         isCompleted: false
  //       },
  //       {
  //         id: uuidv4(),
  //         task: "Crear curso 3",
  //         isCompleted: false
  //       }
  //     ],
  //     isDesktop: true,
  //     aColor: "white",
  //     fontSize: 20,
  //     newTask: null,
  //   }
  // },
  // methods: {
  //   addTask() {
  //     this.tasks.push({
  //       id: uuidv4(),
  //       task: this.newTask,
  //       isCompleted: false
  //     });
  //     this.newTask = null;
  //   }
  // }
}
</script>

<style scoped>
  .bg-goldenrod {
    margin: 1rem;
  }
</style>