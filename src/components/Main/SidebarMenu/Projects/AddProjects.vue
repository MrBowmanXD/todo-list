<template>
  <div
    v-for="(titleProject, index) in NewProjectTitle"
    :key="index"
    :class="NewCreatedProject ? `project${index} CreatedProjectContainer` : ''"
  >
    <CreatedProject />
    <div>
      {{ titleProject }}
    </div>
  </div>
  <div
    class="AddProjectContainer container"
    v-if="!AtivarFormulario"
    @click="MostrarFormulario"
  >
    <div class="AddProjectIcon">
      <i class="fa-solid fa-plus"></i>
    </div>
    <h4 class="AddProjectTitle">
      {{ title }}
    </h4>
  </div>
  <div class="FormularioContainer" v-if="AtivarFormulario">
    <Formulario
      :FormularioAtivo="AtivarFormulario"
      @clickedAdd="AddActivated"
      @clickedCancel="CancelActivated"
    />
  </div>
</template>

<script>
import Formulario from "./Formulario.vue";
import CreatedProject from "./CreatedProjects/CreatedProject.vue";

export default {
  name: "AddProjects",
  components: {
    Formulario,
    CreatedProject,
  },
  data() {
    return {
      title: "Add Project",
      AtivarFormulario: false,
      NewCreatedProject: false,
      NewCreatedProjectTitle: [],
      NewProjectTitle: [],
      temporaryProject: "",
    };
  },
  methods: {
    MostrarFormulario() {
      this.AtivarFormulario = true;
    },
    CancelActivated(value) {
      if (value === false) {
        this.AtivarFormulario = false;
      }
    },
    AddActivated(value) {
      if (value[0] === true) {
        this.NewCreatedProject = true;
        this.AtivarFormulario = false;
        this.NewProjectTitle.push(value[1]);
        setTimeout(() => {
          for (let i = 0; i < this.NewProjectTitle.length; i++) {
            let project = document.querySelector(`.project${i}`);
            project.addEventListener("click", (e) => {
              let projects = document.querySelectorAll(".CreatedProjectContainer");
              projects.forEach((project) => {
                project.classList.remove("ativo");
              });

              if (e.target == project) {
                project.classList.add("ativo");
              }
            });
          }
        }, 1000);
      }
    },
  },
};
</script>

<style scoped>
.AddProjectContainer,
.CreatedProjectContainer {
  display: flex;
  align-items: center;
  padding: 15px;
  cursor: pointer;
}
.AddProjectContainer:hover,
.CreatedProjectContainer:hover {
  background-color: #1cac78;
}

.CreatedProjectContainer li {
  text-decoration: none;
}

.AddProjectTitle {
  font-weight: 300;
  font-size: 24px;
}
.AddProjectIcon {
  margin-right: 15px;
}
.ativo {
  background-color: #1cac78;
}
</style>
