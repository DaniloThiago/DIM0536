<template>
    <div class="item">
        <span class="click" @click="handlerClick">
            {{ title }} ({{ valor }}):
        </span> {{ quantidade }}
        <button @click="handlerPlus">+</button>
        <button @click="handlerMinus">-</button> = R$ {{ (valor * quantidade).toFixed(2) }}
    </div>
</template>

<script lang="ts" setup>
    import { ref } from 'vue';
    type ProdutoProps = { title: string, sub: string, valor: number }
    const produto = defineProps<ProdutoProps>()
    const quantidade = ref(0)
    const handlerClick = () => {
        alert(`Você clicou no item: ${produto.title}`)
    }
    const handlerPlus = () => {
        quantidade.value++
    }
    const handlerMinus = () => {
        quantidade.value--
    }
</script>

<style>
    .item {
        display: flex;
    }
    .click {
        cursor: pointer;        
    }
    button {
        border: 1px solid black;
        padding: 0;
        width: 1.5rem;
        height: 1.5rem;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0.1rem;
    }
</style>