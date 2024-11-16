<template>
  <div class="section">
    <layout/>
  </div>
</template>


<script>
import Layout from "@/components/Layout.vue";
export default {
  components: {
    Layout,
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-decoration: none;
    list-style: none;
  }
  :root{
    --common-width: 1200px;
    --table-width: 1050px
  }

</style>

<style scoped>
  .section{
    background-color: blueviolet;
    padding: 10px;
  }
</style>