<script>
	export default {
		name: 'Header',
	}
</script>

<template>
	<div class="announcement">
		<span>🎉</span>
		<a href="https://github.com/musiqueJS/musiqueJS/releases/tag/v1.2.0" target="_blank">
			Musique.js v1.2.0 is released!
		</a>
		<span>🎉</span>
	</div>
	<div class="header">
		<h2>
			Imagine a world where you can create music without
			<span class="subtitle">any musical knowledge</span>.
		</h2>
		<h1>Musique.js</h1>
		<p>Musique.js is a Javascript library that allows you to create music based on the Web Audio API.</p>

		<a class="arrow" href="#explore"><img src="../assets/arrow-down.png"></a>
	</div>
</template>

<style scoped>
	.announcement {
		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		height: 10vh;
		margin-top: 20px;
		background: linear-gradient(-110deg, #7000ff, #dc33db, #f53a4f);
	}

	.announcement span {
		font-size: 1.2rem;
		margin: 0 1rem;
	}
	
	.announcement a {
		font-size: 1.2rem;
		color: #fff;
		text-decoration: underline;
		text-underline-offset: 5px;
	}

	.announcement a:hover {
		text-underline-offset: 8px;
		transition: text-underline-offset 0.3s ease-in-out;
	}

	.header {
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
	.subtitle {
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

	.arrow {
		position: absolute;
		bottom: 0;
		animation: bounce 1s infinite;
	}
	img {
		height: 2rem;
	}

	@media screen and (max-width : 1024px) {
		h2 {
			font-size: 1.5rem;
			width: 80%;
		}
		p {
			max-width: 80%;
			font-size: 1.2rem;
		}
		h1 {
			font-size: 3rem;
		}
		span {
			font-size: 1.5rem;
		}
	}

	@media screen and (max-width : 768px) {
		div {
			height: 60vh;
		}

		h2 {
			font-size: 1.2rem;
			width: 80%;
		}
		p {
			max-width: 80%;
			font-size: 1rem;
		}
		h1 {
			font-size: 2.5rem;
		}
		span {
			font-size: 1.2rem;
		}
	}
</style>
