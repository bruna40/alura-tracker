<template>
    <section>
        <strong class="display">
            {{ tempoDecorrer }}
        </strong>
    </section>
</template>
<script>
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'CronometroTarefa',
    props: {
        tempoEmSegundos: {
            type: Number,
            default: 0
        }
    },
    computed: {
        tempoDecorrer () {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substring(19,11)
        }
    }
})
</script>
<style scoped>
    .display {
        color: var(--text-primario);
    }
</style>