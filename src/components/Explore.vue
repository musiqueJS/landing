<script lang="ts">
	import NavButton from './NavigationBar/NavButton.vue'

	export default {
		name: 'Explore',
		components: { NavButton },
	}
</script>

<template>
	<div id="explore" class="container">
		<div class="announcement-wrapper">
			<div class="announcement">
				<code>
					<p><span>npm install</span> musiquejs</p>
					<span class="comment-code">// or</span>
					<p><span>yarn add</span> musiquejs</p>
				</code>
			</div>
		</div>
	</div>
	<div class="explore">
		<div class="demo-text">
			<h2>Open your creativity</h2>
			<p>
				With Musique.js, you can create music without any musical knowledge. You
				can create a simple melody, or a complex song with multiple instruments.
			</p>
			<NavButton
				text="Join Waitlist ->"
				color="#7000FF"
				background-color="#fff"
				border-color="#A87FFB"
				hoverColor="#fff"
				hoverBackgroundColor="transparent"
				hoverBorderColor="#cccccc30"
				link="#waitlist"
			/>
		</div>
		<div class="demo-mockup">
			<img src="../assets/electro_album_cover.png" alt="Album cover">
		</div>
	</div>
</template>

<style scoped>
	.container {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 50vh;
		position: relative;
		min-width: 90%;
		margin: 0 auto;
	}
	.announcement-wrapper {
		min-width: 40%;
		padding: 1rem;
		position: relative;
		/* #7000FF */
		/* #DC33DB */
		/* #F53A4F */
		background: linear-gradient(-110deg, #7000ff, #dc33db, #f53a4f);
		padding: 3px;
		border-radius: 15px;
	}
	.announcement {
		background: #222;
		color: white;
		padding: 2rem;
		border-radius: 15px;
	}

	.announcement code {
		font-size: 1.5rem;
	}

	.announcement code span {
		color: #dc33db;
	}

	.announcement code .comment-code {
		color: #ffffff4b;
		font-size: 1rem;
	}

	.explore {
		min-height: 60vh;
		width: 80vw;
		margin: 0 auto;
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		border-radius: 15px;
		position: relative;
		display: flex;
		align-items: center;
	}

	.demo-mockup {
		width: 40vw;
		min-height: 40vh;
		position: absolute;
		top: 31%;
		transform: translateY(-20%);
		right: -100px;
		background: #222;
		border-radius: 15px;
		padding: 2rem;
	}

	.demo-mockup img {
		width: 100%;
	}

	.demo-text {
		width: 40vw;
		min-height: 40vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: flex-start;
		gap: 2rem;
		padding: 2rem;
	}

	.demo-text h2 {
		font-size: 1.5rem;
		color: white;
	}

	.demo-text p {
		font-size: 1.2rem;
		color: white;
	}

	@media screen and (max-width: 1024px) {
		.demo-mockup {
			/* display: none; */
			position: initial;
			top: auto;
			transform: translateY(0);
			right: auto;
			width: 90%;
			margin-bottom: 20px;
		}
		.demo-text {
			width: 100%;
			min-height: 40vh;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;
			gap: 2rem;
			padding: 2rem;
		}
		.demo-text h2 {
			font-size: 1.5rem;
			color: white;
			text-align: center;
		}
		.demo-text p {
			font-size: 1.2rem;
			color: white;
			text-align: center;
		}
		.explore {
			min-height: 60vh;
			width: 80vw;
			margin: 0 auto;
			background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
			border-radius: 15px;
			position: relative;
			display: flex;
			align-items: center;
			flex-direction: column;
		}
	}
</style>
