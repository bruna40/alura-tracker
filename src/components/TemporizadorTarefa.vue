<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
        <div>
            <cronometroTarefa :tempoEmSegundos="tempoEmSegundos" />
        </div>
        <button class="button" @click=" iniciarContagem(event)" :disabled="cronometroRodando" >
            <span class="icon">
                <i class="fas fa-play"></i>
            </span>
            <span>Play</span>
        </button>
        <button class="button" @click=" pararContagem(event)" :disabled="!cronometroRodando">
            <span class="icon">
                <i class="fas fa-stop"></i>
            </span>
            <span>Stop</span>
        </button>
    </div>
</template>
<script>
import { defineComponent } from 'vue'
import cronometroTarefa from './CronometroTarefa.vue'

export default defineComponent({
    name: 'TemporizadorTarefa',
    emits: ['aoTemporizadorParar'],
    components: {
        cronometroTarefa
    },
    data () {
        return {
            tempoEmSegundos: 0,
            cronometro: 0,
            cronometroRodando: false
        }
    },
    methods: {
        iniciarContagem() {
            this.cronometroRodando = true
            this.cronometro = setInterval(() => {
                this.tempoEmSegundos++
            }, 1000)

        },
        pararContagem() {
            this.cronometroRodando = false
            clearInterval(this.cronometro)
            this.$emit('aoTemporizadorParar', this.tempoEmSegundos)
            this.tempoEmSegundos = 0
        }
    }
})
</script>