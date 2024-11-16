<template>
<div class="task-container">
  <div class="name-container">
    <h3>{{name}}</h3>
  </div>
  <slot class="description-container">

  </slot>
</div>

</template>>

<script>
export default {
  data(){
    return{

    }
  },
  props: ['name'],

}
</script>

<style scoped>
  .task-container {
    padding: 10px;
    width: 100%;
    height: 70px;
    border: 1px solid black;
    cursor: pointer;
  }
</style>