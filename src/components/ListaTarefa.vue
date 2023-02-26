<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
                <p>{{ tarefa.descricao }}</p>
            </div>
            <div class="column">
                <CronometroTarefa :tempoEmSegundos="tarefa.tempoEmSegundos" />
            </div>
        </div>
    </div>
</template>
<script>
    import { defineComponent } from 'vue'
    import CronometroTarefa from './CronometroTarefa.vue'

    export default defineComponent({
        name: 'ListaTarefa',
        components: {
            CronometroTarefa
        },
        props: {
            tarefa: {
                type: Object,
                required: true
            }
        }
    })
</script>
<style scoped>
    .box {
        background: #FAF0CA;
    }
</style>