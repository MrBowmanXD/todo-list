<template>
  <form>
    <div class="InputContainer">
      <input type="text" name="projeto" class="AddProjectInput" id="AddProjectInput">
    </div>
    <div class="ButtonContainer">
      <AddButton class="green" text="Add" @click="AddProject($event)" />
      <AddButton class="red" text="Cancel" @click="CancelProject($event)" />
    </div>
  </form>
</template>

<script>
  import AddButton from './AddButton.vue';

export default {
  name: 'Formulario',
  props: {
    FormularioAtivo: Boolean,
  },
  components: {
    AddButton
  },
  data() {
    return {
      AtivarFormulario: false,
      CreatedProjectTitle: ''
    }
  },
  methods: {
    AddProject(e) {
      e.preventDefault();
      console.log(document.querySelector('input').value);
      this.AtivarFormulario = true;
      this.CreatedProjectTitle = document.querySelector('.AddProjectInput').value;
      this.$emit('clickedAdd', [this.AtivarFormulario, this.CreatedProjectTitle]);
    },
    CancelProject(e) {
      e.preventDefault();
      this.AtivarFormulario = false;
      this.$emit('clickedCancel', this.AtivarFormulario);
    }
  },
  created () {
    this.AtivarFormulario = this.FormularioAtivo;
  }
}
</script>

<style scoped>
  .InputContainer input {
    width: 100%;
  }
  .green {
    background-color: green;
  }
  .red {
    background-color: red;
  }
</style>
