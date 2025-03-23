<template>
    <div class="global-root">
        <EnergyCalculator />
        <footer>
            <p>Projeto de Extensão - 2025.1 (ODS 4 & ODS 12)</p>
            <p>Desenvolvido por <a href="https://github.com/jsrwell" target="_blank"
                    rel="noopener noreferrer">jsrwell</a></p>
        </footer>
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
    background: linear-gradient(135deg, rgba(30, 136, 229, 0.6), rgba(255, 112, 67, 0.6));
    animation: gradientAnimation 30s ease-in-out infinite;
    --primary-color: #1e88e5;
    --secondary-color: #ff7043;
    --accent-color: #e3f2fd;
    --background-color: #f1f8e9;
    --border-color: #90caf9;
    --text-color: #424242;
    --text-light-color: #cddee9;
    --font-family: 'Nunito', sans-serif;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
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

* {
    box-sizing: border-box;
    margin:0;
    padding: 0;
}

footer {
    text-align: center;
    margin-top: 20px;
    padding: 10px 0;
    font-family: var(--font-family);
    color: var(--text-color);
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(5px);
    border-radius: 5px;
    font-size: 14px;
}

footer a {
    color: var(--primary-color);
    text-decoration: none;
    font-weight: 600;
}

footer a:hover {
    text-decoration: underline;
}

@media (max-width: 600px) {
    .global-root {
        padding: 10px;
    }
}
</style>