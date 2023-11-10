<script lang="ts">
	import NavigationBar from './components/NavigationBar.vue';
	import Header from './components/Header.vue';
	import Explore from './components/Explore.vue';
	import Socials from './components/Socials.vue';
	export default {
		name: 'App',
		components: {
			NavigationBar,
			Header,
			Explore,
			Socials
		},
	}
</script>

<template>
	<div id="app">
		<NavigationBar />
		<Header />
		<Explore />
		<Socials />
	</div>
</template>

<style scoped></style>
