<script setup>
</script>

<template>
	<div class="container">

		<section class="calculadora">

			<div class="calculadora__header">
				<h1 class="calculadora__header__titulo">Calculadora</h1>
				<p class="calculadora__header__descricao">em VueJS</p>
			</div>

			<hr>
			
			<form class="calculadora__form">
				<div class="calculadora__form__numbers">
					<input class="calculadora__form__input" type="number" required />
					<input class="calculadora__form__input" type="number" required />
				</div>

				<select class="calculadora__form__input form--select" name="operacao">
					<option value="soma">Somar</option>
					<option value="diminui">Subtrair</option>
					<option value="multiplica">Multiplicar</option>
					<option value="divide">Dividir</option>
				</select>
			</form>

			<p class="resultado">
				0
			</p>

		</section>

	</div>
</template>

<style scoped>
	* {
		font-family: 'Roboto', sans-serif;
	}

	hr {
		border: 1px solid #f5f5e5;
		margin: 24px 0;
	}

	.container {
		width: 400px;
		max-width: 100%;
		margin: 60px auto;
	}

	.calculadora {
		padding: 20px 40px;
		color: #f5f5e5;
		background-color: rgb(147, 165, 151);
		border-radius: 8px;
	}

	.calculadora__form {
		display: flex;
		gap: 8px;
		flex-direction: column;
		margin-bottom: 0;
	}
	
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

	.form--select {
		font-size: 22px;
		font-weight: bold;
	}

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

	.calculadora__header__titulo {
		margin: 20px 0 0 0;
	}
	.calculadora__header__descricao {
		margin: 0;
	}
</style>
