<template>
  <div class="container">
    <Header title="Task Tracker" />
    <AddTask/>
    <Tasks @toggle-task="toggleTask" @delete-task="deleteTask" v-bind:tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue"

export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    deleteTask(id) {
      if(confirm('Are you sure')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
      }
    },
    /*
    toggleTask(id){
      this.tasks[id-1].reminder = !this.tasks[id-1].reminder
    }
    */
   toggleTask(id){
    this.tasks = this.tasks.map( (task) => task.id === id ? {...task, reminder: !task.reminder} : task )
   }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctors Appointment",
        day: "March 1st at 2:30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Meeting at School",
        day: "April 4th at 4:44pm",
        reminder: false,
      },
      {
        id: 3,
        text: "Food shopping",
        day: "August 31th at 3:00am",
        reminder: true,
      },
    ];
  },
};
</script>

<style scoped></style>
