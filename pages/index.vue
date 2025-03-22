<template>
    <div class="global-root">
        <EnergyCalculator />
    </div>
</template>

<script setup>
import EnergyCalculator from '~/components/EnergyCalculator.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700&display=swap');

.global-root {
    position: relative;
    overflow: hidden;
    width: 100%;
    min-height: 100vh;
    padding: 20px;
    /* Gradiente animado com transição suave e imagem de fundo */
    background: linear-gradient(135deg, rgba(30, 136, 229, 0.8), rgba(255, 112, 67, 0.8));
    animation: gradientAnimation 30s ease-in-out infinite;
    /* Variáveis globais com Nunito */
    --primary-color: #1e88e5;
    --secondary-color: #ff7043;
    --accent-color: #e3f2fd;
    --background-color: #f1f8e9;
    --border-color: #90caf9;
    --text-color: #424242;
    --font-family: 'Nunito', sans-serif;
}

.global-root::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: url('/bg.jpg') no-repeat center center;
    background-size: cover;
    z-index: -1;
    transform-origin: center center;
    animation: backgroundAnimation 20s ease-in-out infinite;
}

@keyframes gradientAnimation {
    0% {
        background-position: 0% 50%;
    }

    50% {
        background-position: 100% 50%;
    }

    100% {
        background-position: 0% 50%;
    }
}

@keyframes backgroundAnimation {
    0% {
        transform: scale(1);
    }

    50% {
        transform: scale(1.1);
    }

    100% {
        transform: scale(1);
    }
}

/* Reset e responsividade */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

@media (max-width: 600px) {
    .global-root {
        padding: 10px;
    }
}
</style>