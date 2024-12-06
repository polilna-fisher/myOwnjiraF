<template>
  <TheLayout/>
</template>

<script>
import TheLayout from "@/components/TheLayout.vue";
import {onMounted, provide} from "vue";

export default {
  components: {
    TheLayout,
  },
  setup() {
    let columnList = [
      {id: 1, title: "Backlog"},
      {id: 2, title: "In Progress"},
      {id: 3, title: "In Review"},
      {id: 4, title: "Done"},
    ]
    let taskList = []

    onMounted(() => {


      const savedTasks = localStorage.getItem("taskList");
      taskList = savedTasks ? JSON.parse(savedTasks) : [];

      const savedColumns = localStorage.getItem("columnList");
      columnList = savedColumns
          ? JSON.parse(savedColumns)
          : columnList;

      if (!savedColumns) {
        localStorage.setItem("columnList", JSON.stringify(columnList));
      }
    })
    provide("columnList", columnList);
    provide("taskList", taskList);

    return {
      columnList,
      taskList,
    };

  }
}
</script>

<style lang="scss" scoped>
</style>

<style>
:root {
  --light-grey: #f7f8fa;
  --base-grey: #c6cedb73;
  --dark-blue: #1e2633;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  list-style: none;
  text-decoration: none;
}
</style>