<template>
  <div v-bind:key="task.id" v-for="task in tasks">
    <!-- <Task @delete-task="$emit('delete-task', task.id)" v-bind:task="task"/> -->
    <Task @toggle-task="onDoubleClick(task.id)" @delete-task="onDelete(task.id)" v-bind:task="task"/>
  </div>
</template>

<script>
import Task from "./Task.vue"
export default {
  name: "Tasks",
  props: {
    tasks: Array,
  },
  methods: {
    onDelete(id){
      this.$emit('delete-task', id)
    },
    onDoubleClick(id){
      this.$emit('toggle-task', id)
    }
  },
  components: {
    Task
  },
  emits: ['delete-task'],
};
</script>
