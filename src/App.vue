<script setup>
import { ref, computed } from 'vue';

const numero1 = ref(0);
const numero2 = ref(0);
const operacao = ref('+');

const resultado = computed(() => {
    switch (operacao.value) {
        case '+':
            return numero1.value + numero2.value;
        case '-':
            return numero1.value - numero2.value;
        case '*':
            return numero1.value * numero2.value;
        case '/':
            return numero1.value / numero2.value;
        default:
            return 0;
    }
});

const calcularResultado = () => {
    // Nenhuma alteração é necessária aqui, pois você ainda pode chamar a função calcularResultado como antes.
};
</script>

<template>
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Calculadora Aritmética</title>
    </head>
    <body>
        <div id="app" class="calculator">
            <h1 class="calculator-title">Calculadora Aritmética</h1>
            <h4>Insira os valores e selecione a operação:</h4>
            <div class="calculator-inputs">
                <input type="number" v-model="numero1" @input="calcularResultado" class="calculator-input">
                <input type="number" v-model="numero2" @input="calcularResultado" class="calculator-input">
                <select v-model="operacao" @change="calcularResultado" class="calculator-input">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                </select>
            </div>
            <p class="calculator-result">Resultado: {{ resultado }}</p>
        </div>
    </body>
</template>

<style scoped>
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
}

h4 {
    text-align: center;
}

.calculator {
    background-color: #fff;
    border: 1px solid #ccc;
    border-radius: 5px;
    padding: 20px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

.calculator-title {
    text-align: center;
    font-size: 24px;
    margin-bottom: 20px;
}

.calculator-inputs {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}

.calculator-input {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
    width: 100px;
    margin-right: 16px;
}

.calculator-result {
    text-align: center;
    font-size: 18px;
    font-weight: bold;
}
</style>
