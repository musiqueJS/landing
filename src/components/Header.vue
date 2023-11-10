<script lang="ts">
	export default {
		name: 'Header',
	}
</script>

<template>
	<div>
		<h2>
			Imagine a world where you can create music without
			<span>any musical knowledge</span>.
		</h2>
		<h1>Musique.js</h1>
		<p>Musique.js is a Javascript library that allows you to create music based on the Web Audio API.</p>

		<a href="#explore"><img src="../assets/arrow-down.png"></a>
	</div>
</template>

<style scoped>
	div {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 70vh;
		position: relative;
		min-width: 90%;
		margin: 0 auto;
	}
	h2 {
		font-size: 1.8rem;
		text-align: center;
	}
	p {
		max-width: 40%;
		margin: 1rem auto 0 auto;
		font-size: 1.5rem;
		text-align: center;
		color: rgba(255, 255, 255, 0.4);
	}
	h1 {
		font-size: 4rem;
		text-align: center;
		background: linear-gradient(-90deg, #7000FF, #DC33DB, #F53A4F);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}
	span {
		/* #7000FF */
		/* #DC33DB */
		/* #F53A4F */
		background: linear-gradient(-90deg, #7000FF, #DC33DB, #F53A4F);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	@keyframes bounce {
		0% {
			transform: translateY(0);
		}
		50% {
			transform: translateY(-1rem);
		}
		100% {
			transform: translateY(0);
		}
	}

	a {
		position: absolute;
		bottom: 0;
		animation: bounce 1s infinite;
	}
	img {
		height: 2rem;
	}
</style>
