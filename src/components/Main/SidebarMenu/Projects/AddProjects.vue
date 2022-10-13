<template>
  <div class="CreatedProjectContainer" v-if="NewCreatedProject">
    <CreatedProject />
  </div>

  <div class="AddProjectContainer container" v-if="!AtivarFormulario" @click="MostrarFormulario">
    <div class="AddProjectIcon">
      <i class="fa-solid fa-plus"></i>
    </div>
    <h4 class="AddProjectTitle">
      {{ title }}
    </h4>
  </div>
  <div class="FormularioContainer" v-if="AtivarFormulario">
    <Formulario :FormularioAtivo="AtivarFormulario" @clicked="CancelActivated"/>
  </div>
</template>

<script>
  import Formulario from './Formulario.vue';
  import CreatedProject from './CreatedProjects/CreatedProject.vue';

export default {
  name: 'AddProjects',
  components: {
    Formulario,
    CreatedProject
  },
  data () {
    return {
      title: 'Add Project',
      AtivarFormulario: false,
      NewCreatedProject: true, // set to true in order to style the created project component
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
