<template>
  <div class="container">
    <Header title="Task Tracker" />
    <Tasks v-bind:tasks="tasks" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";

export default {
  name: "App",
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      tasks: [],
    };
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
        day: "March 1st at 2:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Food shopping",
        day: "March 1st at 2:30pm",
        reminder: true,
      },
    ];
  },
};
</script>

<style scoped></style>
