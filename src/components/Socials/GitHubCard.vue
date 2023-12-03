<script>
	export default {
		name: 'GitHubCard',
	}
</script>

<template>
	<div class="container">
		<a
			href="https://github.com/musiqueJS/musiqueJS"
			target="_blank"
		>
			<div class="social-wrapper">
				<div class="social">
					<img
						src="../../assets/github-logo.png"
						alt="GitHub Logo"
					/>
					<div class="social-text">
						<h2>We are open source !</h2>
						<p>Come and contribute to our project on GitHub !</p>
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
		background: linear-gradient(-110deg, #3333334a, #fafafa62);
	}

	.social-wrapper:hover {
		background: linear-gradient(-180deg, #3333334a, #fafafa62);
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
