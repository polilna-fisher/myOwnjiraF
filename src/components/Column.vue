<template>
  <div class="column-container">
    <div class="header-container">
      <h3 class="column-header">{{name}}</h3>
    </div>
    <div class="tasks-container">
      <task v-for="task in tasksList" :key="task.id" :name="task.name"></task>
    </div>
  </div>
</template>


<script>
import Task from "@/components/Task.vue";

export default {
  components:{
    Task,
  },
  data() {
    return {

    }
  },
  mounted() {
    const data = localStorage.getItem('tasksList');
    if (data) {
      this.tasksList = data;
    } else {
      localStorage.setItem('tasksList', JSON.stringify(this.tasksList));
    }
  },
  props: ['name', 'tasksList'],
}

</script>

<style scoped>
  .column-container {
    border: 1px solid black;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
  .header-container{
    text-align: center;
    padding: 15px;
    border: 1px solid black;
    width: 100%;
  }
  .column-header{

  }
  .tasks-container{
    padding: 10px;
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 5px;
  }
</style>