<script setup>
import { reactive } from 'vue';

import Numeros from './components/Numeros.vue';
import Resultado from './components/Resultado.vue';
import Filtro from './components/Filtro.vue';

	const estado = reactive ({
		numero1: 0,
		numero2: 0,
		resultado: 0,
		// soma, diminui, multiplica, divide
		metodo: 'soma',
	});

	function calcular() {
		const { metodo } = estado;

		switch (metodo) {
			case 'soma': {
				return estado.resultado = (estado.numero1 + estado.numero2);
			}
			case 'diminui': {
				return estado.resultado = (estado.numero1 - estado.numero2);
			}
			case 'multiplica': {
				return estado.resultado = (estado.numero1 * estado.numero2);
			}
			case 'divide': {
				if (estado.numero2 == 0) {
					return estado.resultado = 'ERRO!'
				} else {
					return estado.resultado = (estado.numero1 / estado.numero2);
				}
			}
		}
	}

	function atualizaNumero(n, novoNumero) {
		switch (n) {
			case 1: {
				estado.numero1 = parseInt(novoNumero);
				calcular();
				break;
			}
			case 2: {
				estado.numero2 = parseInt(novoNumero);
				calcular();
				break;
			}
		}
	}

	function trocarMetodo(e) {
		estado.metodo = e.target.value;
		calcular();
	}
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
				<Numeros
					:numero1="estado.numero1"
					:editnumero1="event => atualizaNumero(1, event.target.value)"
					:numero2="estado.numero2"
					:editnumero2="event => atualizaNumero(2, event.target.value)"
					:calcula="calcular"
				/>

				<Filtro
					:troca-metodo="event => trocarMetodo(event)"
				/>
			</form>

			<Resultado
				:resultado="estado.resultado"
			/>

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

	.form--select {
		font-size: 22px;
		font-weight: bold;
	}

	.calculadora__header__titulo {
		margin: 20px 0 0 0;
	}
	.calculadora__header__descricao {
		margin: 0;
	}
</style>
