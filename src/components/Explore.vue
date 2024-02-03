<script>
	import NavButton from './NavigationBar/NavButton.vue'
	import { Partition, Note } from 'musiquejs'
	import { library } from '@fortawesome/fontawesome-svg-core'
	import { faPlay, faCopy, faCheck } from '@fortawesome/free-solid-svg-icons'
	import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
	import Prism from 'prismjs'
	import 'prismjs/themes/prism-tomorrow.css'

	export default {
		name: 'Explore',
		components: { NavButton, FontAwesomeIcon },
		data() {
			return {
				copy: false,
			}
		},
		setup() {
			library.add(faPlay, faCopy, faCheck)
		},
		mounted() {
			window.Prism = window.Prism || {}
			window.Prism.manual = true
			Prism.highlightAll()
		},
		methods: {
			playMega() {
				const partition = new Partition(
					[
						new Note('D', 4, 0.18),
						new Note('D', 4, 0.18),
						new Note('D', 5, 0.36),
						new Note('A', 4, 0.54),
					],
					'sine',
					new AudioContext()
				)

				partition.play()
			},
			copyCode() {
				navigator.clipboard.writeText(this.$refs.codeToCopy.textContent)
        .then(() => {
					this.copy = true
					setTimeout(() => {
						this.copy = false
					}, 2000)
        })
        .catch(err => {
					console.error('Could not copy text: ', err)
        });
			},
		},
	}
</script>

<template>
	<div
		id="explore"
		class="container"
	>
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
				text="Try it now !"
				color="#7000FF"
				background-color="#fff"
				border-color="#A87FFB"
				hoverColor="#fff"
				hoverBackgroundColor="transparent"
				hoverBorderColor="#cccccc30"
				link="https://demo.musiquejs.com"
			/>
		</div>
		<div class="snippet">
			<!-- <img
				src="../assets/snippet.png"
				alt="snippet-musiquejs"
				draggable="false"
			/> -->
			<font-awesome-icon v-if="!copy" class="copy-icon" icon="copy" @click="copyCode" />
			<font-awesome-icon v-else class="copy-icon" icon="check" @click="copyCode" />
			<pre>
					<code class="language-javascript" ref="codeToCopy">
const partition = new Partition(
	[
		new Note('D', 4, 0.18),
		new Note('D', 4, 0.18),
		new Note('D', 5, 0.36),
		new Note('A', 4, 0.54),
	], // notes

	'sine', // instrument

	new AudioContext() // audio context
)
			</code>
			</pre>
			<button
				class="snippet-play"
				@click="playMega"
			>
				<font-awesome-icon icon="play" />
			</button>
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
		margin: 0 auto 10rem auto;
		background: linear-gradient(to right, #7000ff, #dc33db, #f53a4f);
		border-radius: 15px;
		position: relative;
		display: flex;
		align-items: center;
	}

	img {
		height: 60vh;
		position: absolute;
		top: 20%;
		transform: translateY(-50%);
		left: 150px;
		border-radius: 15px;
		padding: 2rem;
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

	.snippet {
		position: relative;
	}

	.snippet pre {
		position: absolute;
		left: 150px;
		top: -200px;
		color: #7000ff;
		border: none;
		padding: 1rem 2rem;
		border-radius: 15px;
	}

	.copy-icon {
		position: absolute;
		left: 505px;
		top: -165px;
		z-index: 2;
		cursor: pointer;
		font-size: 1.2rem;
	}

	.copy-icon:hover {
		color: #7000ff;
	}

	.snippet-play {
		position: absolute;
		left: 250px;
		top: 125px;
		background: #fff;
		color: #7000ff;
		border: none;
		padding: 1rem 2rem;
		border-radius: 15px;
		cursor: pointer;
		font-size: 1.5rem;
		width: 200px;
	}
	/* hover has to stay for 2 seconds */
	/* keep hovering effet 2 seconds after leaver the button */
	.snippet-play:hover {
		background: #7000ff;
		color: #fff;
		transition: background-color 0.5s;
	}

	.snippet-play:active {
		transform: scale(0.9);
	}

	@media screen and (max-width: 1024px) {
		img {
			/* display: none; */
			position: initial;
			top: auto;
			transform: translateY(0);
			right: auto;
			width: 90%;
			margin-bottom: 20px;
			object-fit: contain;
		}

		.snippet {
			left: auto;
			top: auto;
			width: 100%;
			margin: 0 auto;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-direction: column;
		}

		.snippet pre {
			position: initial;
			left: auto;
			top: auto;
			width: 90%;
			margin: 0 auto;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-direction: column;
			font-size: 0.8rem;
		}

		.copy-icon {
			left: 85%;	
			top: 5%;
			margin: 0 auto;
		}

		.snippet-play {
			position: initial;
			left: auto;
			top: auto;
			width: 90%;
			margin: 20px auto;
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
