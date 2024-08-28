<script setup>
    const props = defineProps(['resultado']);
</script>

<template>
    <p class="resultado">
        {{ props.resultado }}
    </p>
</template>

<style scoped>
	.resultado {
		color: #f5f5e5;
		background-color: rgb(163, 180, 167);
		padding: 16px;
		margin: 8px 0 28px 0;
		text-align: right;
		font-size: 54px;
		font-family: 'IMB Plex Mono', monospace;
		border-radius: 8px;
	}
</style>