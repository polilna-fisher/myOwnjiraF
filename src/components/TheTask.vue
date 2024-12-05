<template>
  <div class="task_container"
       draggable="true"
       @dragstart="handleDragStart">
    <h3 class="title">Title</h3>

  </div>
</template>

<script>
export default {
  name: 'DraggableItem',
  props: ['transferData'],
  setup(props)  {
    const handleDragStart = event => {
      event.dataTransfer.setData('value', JSON.stringify(props.transferData))
    }

    return { handleDragStart }
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