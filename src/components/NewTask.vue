<template>
<div>
      <input placeholder="task name" v-model="taskName"/>
      <button @click="addTask">Сохранить</button>
      <button @click="$emit('closeModal')">Закрыть</button>
</div>
</template>

<script>
export default {
  props: ['isVisible'],
  emits: ['closeModal'],
  methods: {
    addTask() {
      // {id: 1, title: 'the first task', tag: 'qwe', columnId: 1}
      const tasks = JSON.parse(localStorage.getItem('taskList'))
      const newTask = {id: new Date().getTime(), title: this.taskName, tag: 'qwe', columnId: 1};
      if(tasks){
        localStorage.setItem('taskList', JSON.stringify([...tasks, newTask]))
      }else{
        localStorage.setItem('taskList', JSON.stringify(newTask))

      }


    }

  },
  data(){
    return {
      taskName: ''
    }
  }
}
</script>

<style scoped>


</style>