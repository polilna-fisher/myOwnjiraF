
<template>
  <div class="container">
  <Menu :taskList="tasksList"/>
    <div class="table-container">
      <column class="table-column"
           v-for="column in columns"
           :key="column.id"
           :name="column.name"
            :taskList="tasksList">

      </column>
    </div>
  </div>
  <AddTask></AddTask>
</template>


<script>
import Column from "@/components/Column.vue";
import Menu from "@/components/Menu.vue";
import AddTask from "@/components/AddTask.vue"
export default {
  components: {Menu, Column, AddTask},
  data(){
    return{
      columns: [
        {id: 'Backlog', name: 'Backlog'},
        {id: 'To Do', name: 'To Do'},
        {id: 'Testing', name: 'Testing'},
        {id: 'Closed', name: 'Closed'},
      ],
      tasksList: []
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



}
</script>

<style scoped>
  .container{
    background-color: antiquewhite;
    height: 100%;
    width: 100%;
    max-width: var(--common-width);
    margin: 0 auto;
    display: flex;
    gap: 10px;
    padding: 10px;
  }
  .table-container{
    max-width: var(--table-width);
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
</style>