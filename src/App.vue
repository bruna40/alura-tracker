<template>
  <main class="columns is-gapless is multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormularioTarefa @aoSalvarTarefa = 'adicionarTarefa' />
      <div class="list">
        <ListaTarefa v-for="(tarefa, index) in tarefas" :tarefa = "tarefa" :key="index" />
      </div>
    </div>
  </main>
</template>

<script>
import { defineComponent } from 'vue'
import BarraLateral from './components/BarraLateral.vue'
import FormularioTarefa from './components/FormularioTarefa.vue'
import ListaTarefa from './components/ListaTarefa.vue';

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioTarefa,
    ListaTarefa
  },
  data () {
    return {
      tarefas: []
    }
  },
  methods: {
    adicionarTarefa (tarefa) {
      this.tarefas.push(tarefa)
    }
  }
})
</script>

<style>
.list {
  padding: 1.25rem;
}

</style>
