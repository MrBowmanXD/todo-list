<template>
  <ProjectsTitle />
  <AddProjects />
</template>

<script>
  import AddProjects from './AddProjects.vue';
  import ProjectsTitle from './ProjectsTitle.vue';

export default {
  name: 'Projects',
  components: {
    ProjectsTitle,
    AddProjects
  }
}
</script>

<style scoped>

</style>
