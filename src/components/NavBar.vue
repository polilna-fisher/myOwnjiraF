<template>
  <div class="navbar">
    <button class="navbar-item" @click="openModal">Add new item</button>
    <TheModal :isVisible="isModalVisible" @closeModal="closeModal">
      <NewTask/>
    </TheModal>

  </div>
</template>

<script>
import TheModal from "@/components/TheModal.vue";
import NewTask from "@/components/NewTask.vue";
export default {
  components: {TheModal, NewTask},
  data() {
    return {
      isModalVisible: false
    }
  },
  methods: {
    openModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  }
}

</script>


<style scoped>
  .navbar{
    width: 100%;
    max-width: 200px;
    border-right: 1px solid var(--base-grey);
    height: 100vh;
  }
  .navbar-item{
    cursor: pointer;
  }
</style>