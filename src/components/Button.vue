<template>
  <button class="button">
      {{mode}}
  </button>
</template>

<script>
export default {
  data() {
    return {

  }
  },
  props: ['mode'],
}
</script>

<style scoped>
  .button {
    width: 50px;
    height: 50px;
    cursor: pointer;
    color: blue;
  }
</style>