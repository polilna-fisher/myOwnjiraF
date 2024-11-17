<template>
  <form class="add-task-form" @submit.prevent="submitData">
    <div>
      <label for="title">Title </label>
      <input type="text" placeholder="title" id="title" name="title" ref="titleInput" />
    </div>
    <div>
      <label for="description">Description </label>
      <textarea type="text" placeholder="description" id="description" name="description" rows="3"  ref="descriptionInput" />
    </div>
    <button type="submit" >Add Task</button>
  </form>
</template>

<script>
export default {
  methods: {
    submitData(){
      const enteredTitle = this.$refs.titleInput.value;
      const enteredDescription = this.$refs.descriptionInput.value;
      const newTask = {
        id: new Date().toISOString(),
        name: enteredTitle,
        description: enteredDescription,
        column: 'Backlog'
      }
      const currentData = JSON.parse(localStorage.getItem('tasksList'));
      console.log(currentData, newTask, 'dfgdfgdfgrrrwqqqqq')
      localStorage.setItem('tasksList', JSON.stringify([...currentData, newTask]));

    },
  }
}

</script>

<style scoped>
  .add-task-form{
    width: 200px;
    height: 200px;
    background-color: brown;
  }

</style>