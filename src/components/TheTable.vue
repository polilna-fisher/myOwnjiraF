
<template>
  <div class="table_container">
    <div>
      <h3 class="table_header">Backlog</h3>
    </div>
    <div>
      <h3 class="table_header">In Progress</h3>
    </div>
    <div>
      <h3 class="table_header">In Review</h3>
    </div>
    <div>
      <h3 class="table_header">Done</h3>
    </div>
    <div class="main_content">
      <TheTask/>
      <TheTask/>
      <TheTask/>
      <TheTask/>
    </div>
    <div class="main_content">
      <TheTask/>
      <TheTask/>
    </div>
    <div class="main_content">
      <TheTask/>
      <TheTask/>
      <TheTask/>
    </div>
    <div class="main_content">
      <TheTask/>
      <TheTask/>
    </div>

  </div>

</template>

<script>
import TheTask from "@/components/TheTask.vue";
export default {
  components: {TheTask}
}
</script>


<style scoped>
.table_container {
  padding: 10px;
  text-align: center;
  margin: 0 auto;
  display: grid;
  width: 100%;
  grid-template-columns: [Backlog] 1fr [In Progress] 1fr [In Review] 1fr [Done] 1fr;
  grid-template-rows: auto;
  justify-content: space-between;
  align-items: center;
  grid-template-areas:
    "table_header table_header table_header table_header"
    "main_content main_content main_content main_content"
}
.table_header {
  grid-area: table_header;
  color: var(--dark-blue);
  margin-bottom: 40px;
}
.main_content{
  margin: 0 auto;
}
</style>