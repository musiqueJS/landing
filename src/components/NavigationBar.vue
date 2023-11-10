<script lang="ts">
	import NavButton from './NavigationBar/NavButton.vue'
	export default {
		name: 'NavigationBar',
		components: { NavButton },
		data() {
			return {
				burgerIcon: '☰',
				showMobileNav: false,
			}
		},
		methods: {
			toggleMobileNav() {
				this.showMobileNav = !this.showMobileNav
				if (this.showMobileNav) {
					this.burgerIcon = 'x'
				} else {
					this.burgerIcon = '☰'
				}
			},
		},
	}
</script>
<template>
	<div>
		<h2>Mjs</h2>
		<nav class="nav-desktop">
			<ul>
				<li><a href="#">Documentation</a></li>
				<li>
					<NavButton
						text="Explore Musique"
						color="#B6B9CF"
						background-color="transparent"
						border-color="#cccccc30"
						hoverColor="#7000FF"
						hoverBackgroundColor="#fff"
						hoverBorderColor="#A87FFB"
						link="#explore"
					/>
				</li>
				<li>
					<NavButton
						text="Join Waitlist ->"
						color="#fff"
						background-color="#dc33db"
						border-color="#cccccc30"
						hoverColor="#7000ff"
						hoverBackgroundColor="#fff"
						hoverBorderColor="#A87FFB"
						link="#waitlist"
					/>
				</li>
			</ul>
		</nav>
		<div
			class="burger-menu"
			@click="toggleMobileNav()"
		>
			{{ burgerIcon }}
		</div>
		<nav class="nav-mobile" v-if="showMobileNav">
			<ul>
				<li><a href="#" @click="toggleMobileNav()">Documentation</a></li>
				<li><a href="#explore" @click="toggleMobileNav()">Explore Musique</a></li>
				<li><a href="#waitlist" @click="toggleMobileNav()">Join Waitlist</a></li>
			</ul>
		</nav>
	</div>
</template>
<style scoped>
	img {
		height: 2rem;
	}
	div {
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 95%;
		height: 10vh;
		margin: 0 auto;
		border-bottom: 1px solid #cccccc1c;
	}

	h2 {
		font-size: 1.5rem;
		text-align: center;
		background: linear-gradient(-90deg, #7000ff, #dc33db, #f53a4f);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	ul {
		display: flex;
		list-style: none;
		gap: 20px;
		align-items: center;
	}

	li {
		position: relative;
	}

	li:first-child::after {
		content: '';
		position: absolute;
		bottom: -5px;
		left: 0;
		height: 1px;
		width: 0;
		background-color: white;
		transition: width 0.3s ease-in-out;
	}

	li:first-child:hover::after {
		width: 100%;
	}

	a {
		text-decoration: none;
		color: #fff;
		font-weight: bold;
		font-size: 0.8rem;
	}

	a:hover {
		color: #b6b9cf;
	}

	.burger-menu {
		display: none;
	}

	.nav-mobile {
		display: none;
	}

	@media screen and (max-width: 768px) {
		div {
			flex-direction: column;
			height: 20vh;
			border: none;
		}
		ul {
			padding-top: 40px;
			flex-direction: column;
			gap: 30px;
		}

		li {
			border-bottom: 1px solid #cccccc7e;
			padding-bottom: 10px;

		}

		li a {
			font-size: 1.2rem;
		}

		li:first-child::after {
			display: none;
		}

		.burger-menu {
			display: block;
			font-size: 3rem;
			cursor: pointer;
			width: 50px;
			height: 50px;
			position: absolute;
			top: 30px;
			right:-5px;
			margin: 1rem;
			display: flex;
			justify-content: center;
			align-items: center;
			z-index: 2;
		}

		.nav-desktop {
			display: none;
		}

		.nav-mobile {
			display: block;
			background: linear-gradient(-90deg, #7000ff, #dc33db, #f53a4f);
			width: 100%;
			border-radius: 15px;
			padding: 1rem 0 3rem 0;
			position: absolute;
			top: 40px;
			right: 0;
			z-index: 1;
		}
	}
</style>
