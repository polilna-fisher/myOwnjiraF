<template>
  <div class="table_container"
  >
    <div class="column" v-for="column in columnList"
         :key="column.id"
         @drop="onDrop($event, column)"
         @dragover.prevent
         @dragenter.prevent
         >
      <h3 class="table_header">{{ column.title }}</h3>
      <div class="column_content">
        <TheTask v-for="task in taskList.filter(i => i.columnId === column.id)"
                 :key="task.id"
                 :task="task"
                 draggable="true"
                 @dragstart="startDrag($event, task)"/>
      </div>
    </div>
  </div>

</template>

<script>
import TheTask from "@/components/TheTask.vue";

export default {
  inject: ['columnList', 'taskList'],
  data() {
    return {

    }
  },
  components: {TheTask},
  methods: {
    startDrag(event, item) {
      event.dataTransfer.dropEffect = 'move'
      event.dataTransfer.effectAllowed = 'move'
      event.dataTransfer.setData('taskID', item.id)
    },
    onDrop(event, column) {
      const taskID = event.dataTransfer.getData('taskID')
      const task = this.taskList.find((task) => task.id == taskID)
      task.columnId = column.id
      localStorage.setItem("taskList", JSON.stringify(this.taskList));

    },

  },
}
</script>


<style scoped>
.table_container {
  padding: 10px;
  text-align: center;
  margin: 0 auto;
  display: flex;
  width: 100%;
  justify-content: space-between;
}

.column {
  width: 100%;
  max-width: 240px;

}

.table_header {
  grid-area: table_header;
  color: var(--dark-blue);
  margin-bottom: 40px;
}

.column_content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

</style>