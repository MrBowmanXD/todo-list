<template>
  <form v-if="AtivarFormulario">
    <div class="InputContainer">
      <input type="text" name="projeto" id="add-project">
    </div>
    <div class="ButtonContainer">
      <AddButton text="Add" @click="AddProject($event)" />
      <AddButton text="Cancel" @click="CancelProject($event)" />
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
    }
  },
  methods: {
    AddProject(e) {
      e.preventDefault();
      console.log(document.querySelector('input').value);
    },
    CancelProject(e) {
      e.preventDefault();
      this.AtivarFormulario = false;
      this.$emit('clicked', this.AtivarFormulario);
    }
  },
  created () {
    this.AtivarFormulario = this.FormularioAtivo;
  }
}
</script>

<style scoped>

</style>
