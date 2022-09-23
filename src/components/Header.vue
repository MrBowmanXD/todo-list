<template>
  <header class="Container">
    <h1 class="center">
    {{ title }}
  </h1>
</header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      title: 'Todo List'
    }
  }
}
</script>

<style scoped>
  .Container {
    height: 10vh;
  }
</style>
