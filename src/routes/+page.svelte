<script>
	let contador = 0;
	function incrementar() {
		contador += 1;
	}
	function decrementar() {
		contador -= 1;
	}

	let numero = Math.floor(Math.random() * 20); 
	let intentos = 0;
	let numIngresado;

	function guaradarNum() {
		numIngresado = document.getElementById('numIngresado').value;
		intentos++;
	}
	function reiniciar() {
		intentos = 0;
		numero = Math.floor(Math.random() * 20);
	}

	// function resetGuess() {
	// 	return new Promise((resolve) => {
	// 		setTimeout(() => {
	// 			resolve('resolved');
	// 			reiniciar();
	// 		}, 1500);
	// 	});
	// }
	// async function asyncReset() {
	// 	await resetGuess();
	// }
</script>

<h3>Adivinanza de numeros</h3>
<label for="Number" class="text">Adivine el numero elegido de forma aleatoria entre 1 y 20</label>
<input type="number" min="0" max="20" id="numIngresado" placeholder="0" />
<button on:click={guaradarNum}>Elegir</button>
{#if numIngresado > numero}
	<p class="text">El numero es mas bajo</p>
{:else if numIngresado < numero}
	<p class="text">El numero es mas alto</p>
{/if}
{#if numIngresado == numero}
	<p class="text">
		Adivinaste el numero {numero} en {intentos}
		{intentos === 1 ? ' intento' : ' intentos'}
	</p>
	<!-- {asyncReset()} -->
{/if}
<button on:click={reiniciar} id="reset-button">Reiniciar</button>

<h1 class="text">Contador</h1>
<div>
	<button on:click={decrementar} class="count-button" id="decrease-button">-</button>
	<h2>{contador}</h2>
	<button on:click={incrementar} class="count-button" id="increase-button">+</button>
</div>

<!-- <p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p> -->

<style>
	h2 {
		text-align: center;
		font-family: Arial, Helvetica, sans-serif;
		font-size: 80px;
		color: rgb(177, 177, 177);
	}
	h3 {
		font-size: 60px;
		color: rgb(177, 177, 177);
		font-family: Arial, Helvetica, sans-serif;
		margin: 20px;
	}
	.text {
		color: rgb(177, 177, 177);
		font-family: Arial, Helvetica, sans-serif;
		font-size: 25px;
	}
	label {
		color: rgb(177, 177, 177);
		width: 50%;
		padding-top: 0px;
		margin-top: 0px;
	}
	input {
		background-color: rgb(23, 22, 22);
		border-radius: 5px;
		height: 25px;
		width: 80px;
		margin: 18px;
		border: 1px solid rgb(125, 125, 125);
		text-align: left;
		font-size: 16px;
		padding-left: 10px;
		overflow: scroll;
		color: rgb(193, 193, 193);
	}
	button {
		margin: 10px;
		border-radius: 20px;
		border: none;
		cursor: pointer;
		text-align: center;
		height: 45px;
		width: 130px;
		background-color: #3235ca;
		color: rgb(177, 177, 177);
		font-family: Arial, Helvetica, sans-serif;
		background: radial-gradient(circle at 25% 25%, #3235ca8a, #3235ca8a);
		box-shadow:
			0 8px 0 #1a1b639b,
			2px 12px 10px rgba(0, 0, 0, 0.35);
		text-shadow:
			-1px -1px 2px rgba(0, 0, 0, 0.3),
			1px 1px 2px rgba(255, 255, 255, 0.4);
		text-transform: uppercase;
		transform: translate(0, -8px);
		transition: all 0.2s;
	}

	h1{
		margin-top: 80px;
	}
	button:active {
		transform: translate(0, -2px);
		box-shadow:
			0 2px 0 #1a1b639b,
			2px 6px 10px rgba(0, 0, 0, 0.35);
	}
	button:hover {
		background: linear-gradient(0deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.05)), #111337;
		transition: all 0.2s;
	}
	.count-button:hover {
		background: linear-gradient(0deg, rgba(255, 255, 255, 0.05), rgba(255, 255, 255, 0.05)), #111337;
		transition: all 0.4s;
		/* color: rgb(0, 53, 9); */
	}
	.count-button {
		background-color: #3235ca8a;
		color: rgb(177, 177, 177);
		height: 57.6px;
		width: 100%;
		margin: 0px;
	}
	#decrease-button {
		/* flex-direction: row; */
		justify-content: space-evenly;
		/* align-items: center;  */

		/* float: inline-start; */
		font-size: 30px;
		text-align: center;
	}
	div {
		height: 340px;
		width: 200px;
		/* text-align: center; */
		/* align-items: center; */
		/* align-self: center; */
		/* margin-left: 570px; */
		/* align-content: center; */
		border: 1px solid black;
		border-radius: 20px;
		background-color: #111337;
	}
	#increase-button {
		/* float: right; */
		/* flex-direction: row; */
		justify-content: space-evenly;
		font-size: 25px;
		text-align: center;
	}
</style>
