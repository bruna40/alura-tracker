<template>
<div class="box">
    <div class="columns">
        <div class="column is-8" role="form" aria-label="Formulario para criação de uma nova tarefa">
            <input type="text" class="input" placeholder="Digite o nome da tarefa" />
        </div>
        <div class="column">
            <section>
                <strong>00:00:00</strong>
            </section>
            <button class="button">
                <span class="icon">
                    <i class="fas fa-play"></i>
                </span>
                <span>Play</span>
            </button>
            <button class="button">
                <span class="icon">
                    <i class="fas fa-stop"></i>
                </span>
                <span>Stop</span>
            </button>
        </div>
    </div>
</div>
</template>
<script>
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'FormularioTarefa'
})
</script>
<style>
</style>