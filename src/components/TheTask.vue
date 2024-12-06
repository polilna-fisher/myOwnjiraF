<template>
  <div class="task_container">
    <h3 class="title">Title {{task.id}}</h3>

  </div>
</template>

<script>
export default {
  props: ['task'],
  methods: {

  }
}
</script>

<style scoped>
.task_container{
  padding: 10px;
  width: 200px;
  height: 150px;
  background-color: white;
  margin-bottom: 10px;
  border-radius: 15px;
  cursor: pointer;
  -webkit-box-shadow: 2px 4px 17px 1px rgba(34, 60, 80, 0.2);
  -moz-box-shadow: 2px 4px 17px 1px rgba(34, 60, 80, 0.2);
  box-shadow: 2px 4px 17px 1px rgba(34, 60, 80, 0.2);
}
</style>