<template>
  <div class="task">
    <div v-on:dblclick="onDoubleClick(task.id)" v-bind:class="[task.reminder ? 'reminder': '']" class="box">
      <div  class="bag"> 
        <h3>{{ task.text }}</h3>
        <i v-on:click="onDelete(task.id)" class="myIcone fas fa-times"></i>
      </div>
      <p>{{task.day}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
  methods: {
    onDelete(id) {
      this.$emit('delete-task', id)
    },
    onDoubleClick(id){
      this.$emit('toggle-task', id)
    }
  }
};
</script>

<style scoped>
  .task:hover{
    cursor: pointer;
  }
  .box{
    border: 2px solid grey;
    margin-bottom: 10px;
    padding: 10px;
    border-radius: 10px;
  }
  .bag{
    display: flex;
  }
  .myIcone{
    font-size: larger;
    align-self: center;
    margin-left: auto;
    padding-left: 15px ;
    color: red;
  }

  .myIcone:hover{
    cursor: pointer;
  }
</style>