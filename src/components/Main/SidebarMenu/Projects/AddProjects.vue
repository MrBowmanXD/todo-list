<template>
  <div class="AddProjectContainer container" v-if="!AtivarFormulario" @click="MostrarFormulario">
    <div class="AddProjectIcon">
      <i class="fa-solid fa-plus"></i>
    </div>
    <h4 class="AddProjectTitle">
      {{ title }}
    </h4>
  </div>
  <Formulario :FormularioAtivo="AtivarFormulario" @clicked="CancelActivated"/>
</template>

<script>
  import Formulario from './Formulario.vue';

export default {
  name: 'AddProjects',
  components: {
    Formulario
  },
  data () {
    return {
      title: 'Add Project',
      AtivarFormulario: false,
    }
  },
  methods: {
    MostrarFormulario() {
      this.AtivarFormulario = true;
    },
    CancelActivated(value) {
      if (value === false) {
        this.AtivarFormulario =false;
      }
    }
  }
}
</script>

<style scoped>
  .AddProjectContainer {
    display: flex;
    align-items: center;
    padding: 15px;
    cursor: pointer;
  }
  .AddProjectContainer:hover {
    background-color: #1CAC78;
  }

  .AddProjectTitle {
    font-weight: 300;
    font-size: 24px;
  }
  .AddProjectIcon {
    margin-right: 15px;
  }
</style>
