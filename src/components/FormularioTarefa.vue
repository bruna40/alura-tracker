<template>
<div class="box">
    <div class="columns">
        <div class="column is-8" role="form" aria-label="Formulario para criação de uma nova tarefa">
            <input
                type="text"
                class="input"
                placeholder="Digite o nome da tarefa"
                v-model="descricao"
            />
        </div>
        <div class="column">
            <div class="column">
                <TemporizadorTarefa  @aoTemporizadorParar ='finalizarTempo'/>
            </div>

        </div>
    </div>
</div>
</template>
<script>
import { defineComponent } from 'vue'
import TemporizadorTarefa from './TemporizadorTarefa.vue'

export default defineComponent({
    name: 'FormularioTarefa',
    emits: ['aoSalvarTarefa'],
    components: {
        TemporizadorTarefa
    },
    data () {
        return {
            descricao: ''
        }
    },
    methods: {
        finalizarTempo (tempoEmSegundos) {
            this.$emit('aoSalvarTarefa', {
                tempoEmSegundos: tempoEmSegundos,
                descricao: this.descricao
            })
            this.descricao = ''
        }
    }
})
</script>