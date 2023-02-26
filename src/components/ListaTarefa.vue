<template>
    <BoxTarefa>
        <div class="columns">
            <div class="column is-7">
                <p>{{ tarefa.descricao || 'Tarefa sem descrição' }}</p>
            </div>
            <div class="column">
                <CronometroTarefa :tempoEmSegundos="tarefa.tempoEmSegundos" />
            </div>
        </div>
    </BoxTarefa>
</template>
<script>
    import { defineComponent } from 'vue'
    import CronometroTarefa from './CronometroTarefa.vue'
    import BoxTarefa from './BoxTarefa.vue'

    export default defineComponent({
        name: 'ListaTarefa',
        components: {
            CronometroTarefa,
            BoxTarefa
        },
        props: {
            tarefa: {
                type: Object,
                required: true
            }
        }
    })
</script>