<template>
    <div class="container">
        <h1>Calculadora de Eficiência Energética</h1>
        <form @submit.prevent="calculateEnergy">
            <!-- Campo CPU -->
            <div class="form-group">
                <label for="cpu">
                    Potência da CPU (Watts):
                    <span class="info-icon">
                        ℹ
                        <span class="tooltip-content">
                            <table>
                                <caption>Valores base de 2025</caption>
                                <thead>
                                    <tr>
                                        <th>Modelo</th>
                                        <th>Consumo (W)</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Intel Celeron (antigo)</td>
                                        <td>25</td>
                                    </tr>
                                    <tr>
                                        <td>Intel Core i3 (11ª Gen)</td>
                                        <td>35</td>
                                    </tr>
                                    <tr>
                                        <td>Intel Core i5 (12ª Gen)</td>
                                        <td>65</td>
                                    </tr>
                                    <tr>
                                        <td>Intel Core i7 (12ª Gen)</td>
                                        <td>95</td>
                                    </tr>
                                    <tr>
                                        <td>Intel Core i9 (13ª Gen)</td>
                                        <td>125</td>
                                    </tr>
                                    <tr>
                                        <td>AMD Athlon (antigo)</td>
                                        <td>25</td>
                                    </tr>
                                    <tr>
                                        <td>AMD Ryzen 3 (5300G)</td>
                                        <td>45</td>
                                    </tr>
                                    <tr>
                                        <td>AMD Ryzen 5 (5600G)</td>
                                        <td>65</td>
                                    </tr>
                                    <tr>
                                        <td>AMD Ryzen 7 (5800X)</td>
                                        <td>95</td>
                                    </tr>
                                    <tr>
                                        <td>AMD Ryzen 9 (5950X)</td>
                                        <td>105</td>
                                    </tr>
                                </tbody>
                            </table>
                        </span>
                    </span>
                </label>
                <input id="cpu" v-model.number="cpu" type="number" placeholder="ex: 65" required />
            </div>

            <!-- Campo GPU -->
            <div class="form-group">
                <label for="gpu">
                    Potência da GPU (Watts):
                    <span class="info-icon">
                        ℹ
                        <span class="tooltip-content">
                            <table>
                                <caption>Valores base de 2025</caption>
                                <thead>
                                    <tr>
                                        <th>Modelo</th>
                                        <th>Consumo (W)</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>NVIDIA GTX 1050 (antigo)</td>
                                        <td>75</td>
                                    </tr>
                                    <tr>
                                        <td>NVIDIA RTX 2060</td>
                                        <td>160</td>
                                    </tr>
                                    <tr>
                                        <td>NVIDIA RTX 3060</td>
                                        <td>170</td>
                                    </tr>
                                    <tr>
                                        <td>NVIDIA RTX 4050</td>
                                        <td>150</td>
                                    </tr>
                                    <tr>
                                        <td>AMD Radeon RX 7600</td>
                                        <td>130</td>
                                    </tr>
                                </tbody>
                            </table>
                        </span>
                    </span>
                </label>
                <input id="gpu" v-model.number="gpu" type="number" placeholder="ex: 75" required />
            </div>

            <!-- Campo Monitor -->
            <div class="form-group">
                <label for="monitor">
                    Potência do Monitor (Watts):
                    <span class="info-icon">
                        ℹ
                        <span class="tooltip-content">
                            <table>
                                <caption>Valores base de 2025</caption>
                                <thead>
                                    <tr>
                                        <th>Modelo</th>
                                        <th>Consumo (W)</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>CRT (antigo)</td>
                                        <td>60</td>
                                    </tr>
                                    <tr>
                                        <td>LCD 19"</td>
                                        <td>25</td>
                                    </tr>
                                    <tr>
                                        <td>LED 22"</td>
                                        <td>20</td>
                                    </tr>
                                    <tr>
                                        <td>LED 24"</td>
                                        <td>30</td>
                                    </tr>
                                    <tr>
                                        <td>LED 27"</td>
                                        <td>35</td>
                                    </tr>
                                    <tr>
                                        <td>Monitor Curvo 27"</td>
                                        <td>40</td>
                                    </tr>
                                    <tr>
                                        <td>Ultrawide 34"</td>
                                        <td>45</td>
                                    </tr>
                                </tbody>
                            </table>
                        </span>
                    </span>
                </label>
                <input id="monitor" v-model.number="monitor" type="number" placeholder="ex: 30" required />
            </div>

            <!-- Campo Horas de Uso -->
            <div class="form-group">
                <label for="usage">
                    Horas de Uso por Dia:
                    <span class="info-icon">
                        ℹ
                        <span class="tooltip-content">
                            <table>
                                <caption>Valores base de 2025</caption>
                                <thead>
                                    <tr>
                                        <th>Cenário</th>
                                        <th>Horas</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Trabalho</td>
                                        <td>8</td>
                                    </tr>
                                    <tr>
                                        <td>Lazer</td>
                                        <td>4</td>
                                    </tr>
                                    <tr>
                                        <td>Uso intensivo</td>
                                        <td>12</td>
                                    </tr>
                                </tbody>
                            </table>
                        </span>
                    </span>
                </label>
                <input id="usage" v-model.number="usage" type="number" placeholder="ex: 8" required />
            </div>

            <!-- Campo Custo da Energia -->
            <div class="form-group">
                <label for="energyCost">
                    Custo da Energia (R$/kWh):
                    <span class="info-icon">
                        ℹ
                        <span class="tooltip-content">
                            <table>
                                <caption>Dados coletados em 2025</caption>
                                <thead>
                                    <tr>
                                        <th>Companhia</th>
                                        <th>Ano</th>
                                        <th>Valor (R$/kWh)</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td>Copel</td>
                                        <td>2025</td>
                                        <td>0.67</td>
                                    </tr>
                                    <tr>
                                        <td>Enel</td>
                                        <td>2025</td>
                                        <td>0.70</td>
                                    </tr>
                                    <tr>
                                        <td>Eletrobras</td>
                                        <td>2025</td>
                                        <td>0.72</td>
                                    </tr>
                                </tbody>
                            </table>
                            <p class="disclaimer">
                                * Estes valores foram coletados por inteligência artificial e devem ser confirmados nos
                                sites oficiais para assegurar os dados reais.
                            </p>
                        </span>
                    </span>
                </label>
                <input id="energyCost" v-model.number="energyCost" type="number" step="0.01" placeholder="ex: 0.67"
                    required />
            </div>

            <!-- Botão Calcular Centralizado (100% de largura) -->
            <button type="submit" class="calc-button">Calcular</button>
        </form>

        <div v-if="result" class="results">
            <h2>Resultados</h2>
            <p>Potência Total: <span>{{ totalPower }}</span> Watts</p>
            <p>Consumo Diário: <span>{{ dailyKWh.toFixed(2) }}</span> kWh</p>
            <p>Custo Mensal Estimado: <span>R$ {{ monthlyCost.toFixed(2) }}</span></p>
            <h2>Dicas para Eficiência Energética</h2>
            <p>{{ tipMessage }}</p>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const cpu = ref(0)
const gpu = ref(0)
const monitor = ref(0)
const usage = ref(0)
const energyCost = ref(0.67)
const result = ref(false)
const totalPower = ref(0)
const dailyKWh = ref(0)
const monthlyCost = ref(0)
const tipMessage = ref('')

/**
 * Calcula o consumo de energia e atualiza os resultados.
 */
function calculateEnergy() {
    totalPower.value = cpu.value + gpu.value + monitor.value
    dailyKWh.value = (totalPower.value * usage.value) / 1000
    monthlyCost.value = dailyKWh.value * 30 * energyCost.value
    tipMessage.value =
        totalPower.value > 500
            ? "Seu PC consome uma quantidade alta de energia. Considere atualizar para componentes mais eficientes."
            : "Seu PC é relativamente eficiente. Faça manutenções regulares e ajuste as configurações de economia de energia."
    result.value = true
}
</script>

<style scoped>
.container {
    max-width: 600px;
    margin: 40px auto;
    padding: 20px;
    /* Efeito glass sem hover de escala */
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(10px);
    border-radius: 10px;
    border: 1px solid var(--border-color);
    box-shadow: 0 4px 12px rgba(255, 255, 255, 0.3);
    font-family: var(--font-family);
    color: var(--text-color);
}

h1,
h2 {
    text-align: center;
    color: var(--primary-color);
    margin-bottom: 20px;
    transition: color 0.3s;
}

.form-group {
    display: flex;
    flex-direction: column;
    position: relative;
    margin-bottom: 15px;
}

label {
    margin-bottom: 5px;
    font-weight: 600;
    color: var(--text-color);
}

/* Estilização dos inputs */
input {
    padding: 10px;
    border: 1px solid var(--border-color);
    border-radius: 5px;
    transition: border-color 0.3s, box-shadow 0.3s;
    font-family: var(--font-family);
}

input:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 8px var(--primary-color);
}

/* Botão Calcular: centralizado, 100% de largura */
button.calc-button {
    display: block;
    width: 100%;
    padding: 12px;
    background: var(--primary-color);
    color: #fff;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    font-weight: bold;
    cursor: pointer;
    transition: background 0.3s;
    margin-top: 20px;
}

button.calc-button:hover {
    background: var(--secondary-color);
}

/* Resultados */
.results {
    margin-top: 30px;
    padding: 20px;
    background: rgba(255, 255, 255, 0.25);
    backdrop-filter: blur(10px);
    border-radius: 10px;
    border: 1px solid var(--border-color);
}

.results p {
    margin: 10px 0;
    font-size: 16px;
}

.results span {
    font-weight: bold;
    color: var(--primary-color);
}

/* Tooltip - ícone e conteúdo */
.info-icon {
    display: inline-block;
    margin-left: 8px;
    position: relative;
    cursor: help;
    font-size: 16px;
    width: 20px;
    height: 20px;
    line-height: 20px;
    text-align: center;
    border-radius: 50%;
    background-color: var(--secondary-color);
    color: #fff;
    transition: background-color 0.3s;
}

.info-icon:hover {
    background-color: var(--primary-color);
}

.tooltip-content {
    display: none;
    position: absolute;
    top: 120%;
    left: 0;
    z-index: 10;
    width: 250px;
    background: rgba(255, 255, 255, 0.9);
    border: 1px solid var(--border-color);
    border-radius: 5px;
    padding: 10px;
    font-size: 12px;
    color: var(--text-color);
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.info-icon:hover .tooltip-content {
    display: block;
}

/* Mini tabela dentro do tooltip */
.tooltip-content table {
    width: 100%;
    border-collapse: collapse;
}

.tooltip-content caption {
    font-size: 10px;
    margin-bottom: 5px;
    color: var(--text-color);
}

.tooltip-content th,
.tooltip-content td {
    border: 1px solid var(--border-color);
    padding: 4px;
    text-align: center;
}

/* Ajuste para mobile: centraliza tooltip e limita largura */
@media (max-width: 600px) {
    .tooltip-content {
        width: 90vw;
        left: 50%;
        transform: translateX(-50%);
    }
}
</style>