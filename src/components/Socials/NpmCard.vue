<script>
	export default {
		name: 'GitHubCard',
	}
</script>

<template>
	<div class="container">
		<a
			href="https://www.npmjs.com/package/musiquejs"
			target="_blank"
		>
			<div class="social-wrapper">
				<div class="social">
					<img
						src="../../assets/npm-logo.png"
						alt="npm Logo"
					/>
					<div class="social-text">
						<h2>Look at our package !</h2>
						<p>Discover our package on NPM.</p>
					</div>
				</div>
			</div>
		</a>
	</div>
</template>

<style scoped>
	a {
		text-decoration: none;
	}
	.card {
		width: 500px;
	}

	.container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		margin: 0 auto;
	}

	.social-wrapper {
		min-width: 40%;
		padding: 1rem;
		position: relative;
		padding: 3px;
		border-radius: 15px;
		background: linear-gradient(110deg, #CD090D, #fafafa62);
	}

	.social-wrapper:hover {
		background: linear-gradient(0deg, #CD090D, #fafafa62);
	}

	.social {
		background: #05010d;
		color: white;
		padding: 2rem;
		border-radius: 15px;
	}

	.social img {
		height: 40px;
	}

	.social-text h2 {
		font-size: 1.5rem;
	}

	.social-text p {
		color: #ffffff4b;
		font-size: 1rem;
	}

	@media (max-width: 1024px) {
		.social-wrapper {
			min-width: 80%;
		}

		.container {
			height: auto;
		}
	}
</style>
