<script setup>
    const props = defineProps(['trocaMetodo']);
</script>

<template>
    <select @change="props.trocaMetodo" class="calculadora__form__input form--select" name="operacao">
        <option value="soma">Somar</option>
        <option value="diminui">Subtrair</option>
        <option value="multiplica">Multiplicar</option>
        <option value="divide">Dividir</option>
    </select>
</template>