

<template>
  <div class="section">
    <div class="container">
      <NavBar/>
      <TheTable/>
    </div>

  </div>
</template>

<script >
import NavBar from "@/components/NavBar.vue";
import TheTable from "@/components/TheTable.vue";
export default {
  components: {NavBar, TheTable}
}

</script>

<style scoped>
  .section{
    background-color: var(--light-grey);
    width: 100%;
    height: 100%;
    position: relative;

  }
  .container{
    background-color: var(--light-grey);
    width: 100%;
    max-width: 1350px;
    padding: 10px;
    margin: 0 auto;
    display: flex;

  }
</style>