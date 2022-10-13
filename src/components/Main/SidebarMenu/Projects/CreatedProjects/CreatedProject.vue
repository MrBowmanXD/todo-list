<template>
  <div class="Container">
    <div class="IconContainer">
      <i class="fa-solid fa-list-check"></i>
    </div>
    <div class="TitleContainer">
      <h3>
        {{ title }}
      </h3>
    </div>
  </div>

</template>

<script>
export default {
  name: 'CreatedProject',
  data () {
    return {
      title: 'Placeholder'
    }
  }
}
</script>

<style scoped>

</style>
