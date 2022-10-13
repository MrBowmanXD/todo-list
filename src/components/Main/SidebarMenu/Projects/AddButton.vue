<template>
  <button>
    {{ text }}
  </button>
</template>

<script>
export default {
  name: 'AddButton',
  props: {
    text: String
  }
}
</script>

<style scoped>
  button {
    width: 50%;
    border: none;
  }
</style>
