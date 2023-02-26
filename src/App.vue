<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral @ativarModoEscuro="trocarTema"/>
    </div>
    <div class="column is-three-quarter conteudo">
      <FormularioTarefa @aoSalvarTarefa = 'adicionarTarefa' />
      <div class="list">
        <ListaTarefa v-for="(tarefa, index) in tarefas" :tarefa = "tarefa" :key="index" />
        <BoxTarefa v-if="listaEstaVazia">
          Você não está muito produtivo hoje, não é mesmo?
        </BoxTarefa>
      </div>
    </div>

  </main>
</template>

<script>
import { defineComponent } from 'vue'
import BarraLateral from './components/BarraLateral.vue'
import FormularioTarefa from './components/FormularioTarefa.vue'
import ListaTarefa from './components/ListaTarefa.vue';
import BoxTarefa from './components/BoxTarefa.vue'

export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioTarefa,
    ListaTarefa,
    BoxTarefa
  },
  data () {
    return {
      tarefas: []
    }
  },
  computed: {
    listaEstaVazia () {
      return this.tarefas.length === 0
    }
  },
  methods: {
    adicionarTarefa (tarefa) {
      this.tarefas.push(tarefa)
    },
    trocarTema () {
      document.querySelector('main').classList.toggle('modo-noturno')
    }
  }
})
</script>

<style>
.list {
  padding: 1.25rem;
}

main {
  --bg-primario: #FFF;
  --text-primario: #000;
}

main.modo-noturno {
  --bg-primario: #2B2D42;
  --text-primario: #DDD;
}

.conteudo {
  background-color: var(--bg-primario);

}

</style>
