<script setup>
    const props = defineProps(['numero1', 'numero2', 'editnumero1', 'editnumero2', 'calcula']);
</script>

<template>
    <div class="calculadora__form__numbers">
        <input
			required
			class="calculadora__form__input"
			type="number"
			:value="props.numero1"
			@keyup="props.editnumero1"
			@change="calcula"
		/>
        <input
			required
			class="calculadora__form__input"
			type="number"
			:value="props.numero2"
			@keyup="props.editnumero2"
			@change="calcula"
		/>
    </div>
</template>

<style scoped>
	.calculadora__form__input {
		color: #f5f5e5;
		padding: 8px;
		background-color: rgb(163, 180, 167);
		border-radius: 8px;

		outline: none;
		border: none;
	}

	.calculadora__form__numbers {
		display: flex;
		gap: 2%
	}

	.calculadora__form__numbers > .calculadora__form__input {
		width: 46%;
		font-size: 48px;
		text-align: center;

		font-family: 'IMB Plex Mono', monospace;
	}
</style>