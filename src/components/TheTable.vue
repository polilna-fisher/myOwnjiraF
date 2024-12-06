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
import {differenceBy} from 'lodash/fp'
import {computed, ref} from 'vue'
import TheTask from "@/components/TheTask.vue";

export default {
  data() {
    return {
      taskList: [
        {id: 1, title: 'the first task', tag: 'qwe', columnId: 1},
        {id: 2, title: 'the first task', tag: 'qwe', columnId: 1},
        {id: 3, title: 'the first task', tag: 'qwe', columnId: 2},
        {id: 4, title: 'the first task', tag: 'qwe', columnId: 3},
        {id: 5, title: 'the first task', tag: 'qwe', columnId: 4},
        {id: 6, title: 'the first task', tag: 'qwe', columnId: 4}
      ],
      columnList: [
        {id: 1, title: 'Backlog'},
        {id: 2, title: 'In Progress'},
        {id: 3, title: 'In Review'},
        {id: 4, title: 'Done'}
      ],

    }
  },
  components: {TheTask},
  methods: {
    startDrag(event, item) {
      event.dataTransfer.dropEffect = 'move'
      event.dataTransfer.effectAllowed = 'move'
      event.dataTransfer.setData('taskID', item.id)
    },
    onDrop(event, list) {
      const taskID = event.dataTransfer.getData('taskID')
      const task = this.taskList.find((task) => task.id == taskID)
      console.log(list, 't')
      task.columnId = list.id
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