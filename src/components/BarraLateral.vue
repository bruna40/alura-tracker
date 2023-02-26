<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="logo do site" />
        </h1>

        <button class="button" @click="ativarModoEscuro">
            {{ classeModoEscuro }}
        </button>

    </header>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'BarraLateral',
    emits: ['ativarModoEscuro'],
    data () {
        return {
            modoEscuro: false
        }
    },
    computed: {
        classeModoEscuro () {
            return this.modoEscuro ? 'Desativar modo escuro' : 'Ativar modo escuro'
        }
    },
    methods: {
        ativarModoEscuro () {
            this.modoEscuro = !this.modoEscuro
            this.$emit('ativarModoEscuro', this.modoEscuro)
        }
    }
})
</script>
<style scoped>
    header {
        background: #0D3B66;
        width: 100%;
        height: 100vh;
        padding: 1rem;
        text-align: center;
    }
    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    }
</style>
