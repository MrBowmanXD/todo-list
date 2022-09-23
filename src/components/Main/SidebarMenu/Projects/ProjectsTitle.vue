<template>
  <div class="ProjectsTitle">
    <h3>
    {{ title }}
   </h3>
  </div>
</template>

<script>
export default {
  name: 'ProjectsTitle',
  data () {
    return {
      title: 'Projects'
    }
  }
}
</script>

<style scoped>
  .ProjectsTitle {
    padding: 15px;
  }

  .ProjectsTitle h3 {
    font-weight: 600;
    font-size: 24px;
  }
</style>
