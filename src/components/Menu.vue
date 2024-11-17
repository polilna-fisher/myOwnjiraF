<template>
  <div class="menu">
    <Button v-for="mode in modeList"
            :mode="mode.mode"
            :key="mode.id"
            @click="defineAction(mode.mode)"/>
  </div>
</template>



<script>
import Button from "@/components/Button.vue";
import AddTask from "./AddTask.vue";
export default {
  components: {Button, AddTask},
  data() {
    return {
      modeList: [
        {id: 'Add Task', mode: 'addTask'}
      ]
    }
  },
  props: ['taskList'],
  methods: {
    defineAction(mode){
      if(mode === 'addTask'){

      }
    },
  }
}
</script>

<style scoped>
.menu{
  max-width: 80px;
  width: 100%;
  background-color: aquamarine;
  padding: 10px;
  display: flex;
  flex-direction: column;
  gap: 5px;
  align-items: center;
}
</style>