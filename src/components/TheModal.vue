<template>
  <div v-if="isVisible" class="modal-overlay" @click="$emit('closeModal')">
    <div class="modal" @click.stop>
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  props: ['isVisible'],
  emits: ['closeModal'],
  methods: {
  },
  data(){
    return {

    }
  }
}
</script>

<style scoped>
 .modal-overlay{
   width: 100vw;
   height: 100vh;
   background-color: rgba(95, 93, 93, 0.24);
   position: fixed;
   top: 0;
   left: 0;
   display: flex;
   justify-content: center;
   align-items: center;
 }
 .modal{
   background: white;
   padding: 20px;
   border-radius: 8px;
   box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
   max-width: 400px;
   width: 100%;
   text-align: center;
 }

</style>