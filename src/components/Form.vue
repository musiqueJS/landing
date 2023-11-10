<script lang="ts">
export default {
	name: 'Form',
}
</script>

<template>
	<div id="waitlist" class="form">
		<h2>Join Waitlist</h2>
		<p>Get notified when <span>Musique.js</span> is ready for you.</p>
		<form>
			<input type="email" placeholder="Email" />
			<button type="submit">Send</button>
		</form>
	</div>
</template>

<style scoped>
	.form {
		width: 100%;
		height: 40vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin-bottom: 10rem;
	}

	.form > * {
		margin: 1rem;
	}

	.form > form {
		display: flex;
		flex-direction: column;
		width: 100%;
		gap: 1rem;
	}

	.form > form > * {
		margin: 0.5rem;
	}

	.form > form > input {
		margin: 0 auto;
		width: 50%;
		font-size: 1.5rem;
		height: 3rem;
		border: 1px solid #cccccc30;
		border-radius: 0.5rem;
		padding: 0.5rem;
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	.form > form > button {
		font-size: 1.5rem;
		margin: 0 auto;
		width: 20rem;
		height: 3rem;
		border: none;
		border-radius: 0.5rem;
		padding: 0.5rem;
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		color: #fff;
	}

	.form > form > button:hover {
		background: white;
		transform: scale(1.1);
		transition: all 0.3s ease-in-out;
		color: #7000ff;
	}

	h2 {
		font-size: 2rem;
	}

	p {
		font-size: 1.5rem;
	}

	span {
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	@media screen and (max-width: 1024px) {
		.form {
			height: auto;
		}

		.form > form > input {
			width: 80%;
		}

		.form > form > button {
			width: 80%;
		}
	}
</style>