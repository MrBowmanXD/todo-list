<template>
  <main class="MainContainer">
    <Sidebar />
    <MainContent />
  </main>
</template>

<script>
  import Sidebar from './Sidebar.vue';
  import MainContent from './MainContent.vue';

export default {
  name: 'Main',
  components: {
    Sidebar,
    MainContent
  }
}
</script>

<style scoped>
  .MainContainer {
    display: flex;
    height: 80vh;
  }
</style>
