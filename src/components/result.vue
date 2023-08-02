<script setup>
    const props = defineProps(['filtro', 'funcaoSoma', 'funcaoSub', 'funcaoMult', 'funcaoDivisao'])
</script>

<template>
    
        <div class="resultado">
            <p>Resultado:</p>
            <div class="content-resultado">
                <p class="resultado_final" v-if="props.filtro === 'soma'">{{ props.funcaoSoma }}</p>
                <p class="resultado_final" v-else-if="props.filtro === 'subtracao'">{{ props.funcaoSub }}</p>
                <p class="resultado_final" v-else-if="props.filtro === 'multiplicacao'">{{ props.funcaoMult }}</p>
                <p class="resultado_final" v-else>{{ props.funcaoDivisao }}</p>
            </div>
        </div>
   
</template>

<style scoped>
.resultado{
  
    padding: 16px;
    display: flex;
    margin: 0 auto;
    width: 100%;
    max-width: 300px;
    background-color: rgb(228, 231, 231);
    font-size: 1.5rem;
    font-family: sans-serif;
    border-radius: 0 0 10px 10px;
    justify-content: center;
}
.content-resultado{
    margin-left: 10px;
}
.resultado_final{
    font-weight: bold;
    color: red;
}
</style>