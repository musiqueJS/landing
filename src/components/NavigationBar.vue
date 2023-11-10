<script lang="ts">
	import NavButton from './NavigationBar/NavButton.vue';
	export default {
    name: 'NavigationBar',
    components: { NavButton }
}
</script>
<template>
	<div>
		<h2>Mjs</h2>
		<nav>
			<ul>
				<li><a href="#">Documentation</a></li>
				<li><NavButton text="Explore Musique" color="#B6B9CF" background-color="transparent" border-color="#cccccc30" hoverColor="#7000FF" hoverBackgroundColor="#fff" hoverBorderColor="#A87FFB" /></li>
				<li><NavButton text="Join Waitlist ->" color="#05010D" background-color="#A87FFB" border-color="#cccccc30" hoverColor="#7000FF" hoverBackgroundColor="#fff" hoverBorderColor="#A87FFB" /></li>
			</ul>
		</nav>
	</div>
</template>
<style scoped>
	nav {
		border-bottom: 1px solid #cccccc1c;
		padding: 2rem 0;
	}
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
	}
	
	h2 {
		font-size: 1.5rem;
		text-align: center;
		background: linear-gradient(-90deg, #7000FF, #DC33DB, #F53A4F);
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
		color: #B6B9CF;
	}
</style>
