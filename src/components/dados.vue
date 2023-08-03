<script setup>
    const props = defineProps(['valorPrimeiroInput','valorSegundoInput', 'filtro', 'selecionaFiltro'])
</script>

<template>
    <form>
        <div class="container">
            <div class="dados">
                <input @keyup="props.valorPrimeiroInput" type="number" placeholder="00" required>
            </div>
            <div class="sinais">
                <p class="sinais-simbol" v-if="props.filtro === 'soma'"> + </p>
                <p class="sinais-simbol" v-else-if="props.filtro === 'subtracao'">-</p>
                <p class="sinais-simbol" v-else-if="props.filtro === 'multiplicacao'">x</p>
                <p class="sinais-simbol" v-else>÷</p>
            </div>
            <div class="dados">
                <input @keyup="props.valorSegundoInput" type="number" placeholder="00" required>
            </div>
            
        </div>
        <div class="selecao">
                <h3>Escolha a operação:</h3>
                <select @change="props.selecionaFiltro" >
                    <option value="soma"> Soma ( + )</option>
                    <option value="subtracao">Subtração( - )</option>
                    <option value="multiplicacao">Multiplicação( x )</option>
                    <option value="divisao">Divisão (÷)</option>
                </select>
            </div>
    </form>
</template>
<style scoped>
form{
    margin: 0 auto;
    width: 300px;
    background-color: rgb(140, 0, 255);
    padding: 16px;
}
.container{
    display: flex;
    padding: 16px;
    justify-content: space-evenly;
    align-items: center;
}
.dados{
    background-color: aliceblue;
}
.dados input{
width: 60px;
height: 20px;
padding: 5px;
font-size: 18px;
border: none;
text-align: center;
}
.dados input:focus{
    outline: none;
}

.sinais-simbol{
    font-size: 18px;
    font-weight: bold;
    color:aliceblue
}
.selecao{
    color: #fff;
    font-family: sans-serif;
    text-align: center;
}
</style>