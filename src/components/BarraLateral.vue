<template>
    <header>
        <h1>
            <img src="../assets/logo.png" alt="logo do site" />
        </h1>
    </header>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'BarraLateral'
})
</script>
<style scoped>
    header {
        background: #0D3B66;
        width: 100%;
        height: 100vh;
        padding: 1rem;
    }
    @media only screen and (max-width: 768px) {
        header {
            padding: 2.5rem;
            height: auto;
        }
    }
</style>
