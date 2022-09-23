<template>
  <div class="Container" :class="active ? 'ativo' : ''">
    <i class="fa-solid" :class="classeIcon"></i>
    <h4>{{ title }}</h4>
  </div>
</template>

<script>
export default {
  name: 'SideMenuItem',
  props: {
    title: String,
    classeIcon: String,
    classeDiv: String,
    active: Boolean
  }
}
</script>

<style scoped>
  .Container {
    display: flex;
    align-items: center;
    padding: 15px;
    cursor: pointer;
  }

  .Container:hover {
    background-color: #1CAC78;
  }

  .Container h4 {
    font-weight: 300;
    font-size: 24px;
  }

  .fa-solid {
    margin-right: 15px;
  }

  .ativo {
    background-color: #1CAC78;
  }
</style>
