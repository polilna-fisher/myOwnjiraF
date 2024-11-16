
<template>
  <div class="container">
    <div class="menu">

    </div>
    <div class="table-container">
      <column class="table-column"
           v-for="column in columns"
           :key="column.id"
           :name="column.name">

      </column>
    </div>
  </div>
</template>


<script>
import Column from "@/components/Column.vue";
export default {
  components: {Column},
  data(){
    return{
      columns: [
        {id: 'Backlog', name: 'Backlog'},
        {id: 'To Do', name: 'To Do'},
        {id: 'Testing', name: 'Testing'},
        {id: 'Closed', name: 'Closed'},
      ]
    }
  }
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
  .menu{
    max-width: 80px;
    width: 100%;
    background-color: aquamarine;
  }
  .table-container{
    max-width: var(--table-width);
    width: 100%;
    display: flex;
    justify-content: space-between;
  }
</style>