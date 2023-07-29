<template>
<div>
  <Rotulo nome="Nome">
					<input type="text" @input="alterarNome" :value="value.nome">
				</Rotulo>
				<Rotulo nome="Sobrenome">
					<input type="text" @input="alterarSobrenome" :value="value.lastname">
				</Rotulo>
</div>
</template>

<script>
import Rotulo from "./Rotulo.vue";

export default {
  components: { Rotulo },
  props: {
    type: Object,
    required: true,
  },
  methods: {
    alterarNome(event){
      this.$emit('input', { name: event.target.value, lastname: this.value.lastname})
    },
    alterarSobrenome(event){
      this.$emit('input', { name: this.value.name, lastname: event.target.value})
    },
  }
}
</script>

<style>

</style>