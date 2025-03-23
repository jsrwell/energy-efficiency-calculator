# Calculadora de Eficiência Energética

Uma aplicação web estática desenvolvida com **Nuxt 3** para ajudar a calcular o consumo de energia do seu computador. A calculadora utiliza informações sobre a potência (em Watts) de componentes como CPU, GPU e monitor, horas de uso diárias e custo da energia para estimar o consumo e o custo mensal. O projeto traz dicas de eficiência energética e apresenta dados atualizados (base 2025) por meio de tooltips.

## Sumário

- [Calculadora de Eficiência Energética](#calculadora-de-eficiência-energética)
  - [Sumário](#sumário)
  - [Visão Geral](#visão-geral)
  - [Funcionalidades](#funcionalidades)
  - [Tecnologias Utilizadas](#tecnologias-utilizadas)
  - [Instalação e Execução](#instalação-e-execução)
    - [Requisitos](#requisitos)
    - [Passos](#passos)

## Visão Geral

A **Calculadora de Eficiência Energética** foi criada para oferecer uma forma rápida e intuitiva de estimar o consumo energético do seu computador. O usuário informa os valores de consumo dos principais componentes (CPU, GPU, Monitor), as horas de uso diárias e o custo da energia (R$/kWh). Com base nesses dados, o sistema calcula o consumo diário e o custo mensal, além de fornecer dicas para reduzir o consumo e otimizar a eficiência.

O design do projeto é moderno, com um efeito glass (glassmorphism) no card principal, fundo animado com gradiente dinâmico e tipografia com a fonte **Nunito**. Os dados de exemplo apresentados nos tooltips foram coletados para 2025, garantindo informações atualizadas que ajudam o usuário a ter uma referência, embora seja recomendado conferir os dados nos sites oficiais das companhias de energia.

## Funcionalidades

- **Cálculo de Consumo:**
  - Estima o consumo total (Watts) com base na soma dos consumos individuais.
  - Converte o consumo para kWh considerando as horas de uso.
  - Calcula o custo mensal com base no valor informado para a energia.
  
- **Dicas de Economia:**
  - Exibe mensagens de alerta ou incentivo para atualizar componentes, conforme o consumo calculado.

- **Tooltips Interativos:**
  - Cada campo possui um tooltip com tabelas exemplificando valores de consumo de equipamentos (CPU, GPU, Monitor) de modelos antigos a modernos, com dados base de 2025.
  - O campo de custo da energia apresenta um tooltip com informações de companhias, ano base e um disclaimer informando que os valores foram coletados por inteligência artificial e devem ser verificados nos sites oficiais.

- **Design Responsivo e Moderno:**
  - Layout com efeito glass no card.
  - Fundo animado com gradiente dinâmico e imagem de fundo.
  - Otimizado para dispositivos móveis.

## Tecnologias Utilizadas

- **Nuxt 3** – Framework Vue para SSR e geração de sites estáticos.
- **Vue 3** – Biblioteca JavaScript para interfaces reativas.
- **Nitro** – Motor de build utilizado pelo Nuxt 3 para gerar sites estáticos.
- **CSS Glassmorphism** – Efeito visual aplicado no card.
- **Nunito** – Fonte moderna importada do Google Fonts.
- **GitHub Pages** – Hospedagem do site.
- **GitHub Actions** – Pipeline de CI/CD para deploy automático.

## Instalação e Execução

### Requisitos

- Node.js (versão 20 ou superior recomendada)
- npm ou yarn

### Passos

1. **Clone o repositório:**

   ```bash
   git clone https://github.com/jsrwell/energy-efficiency-calculator.git
   cd energy-efficiency-calculator
