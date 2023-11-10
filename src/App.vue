<script lang="ts">
	import NavigationBar from './components/NavigationBar.vue';
	import Header from './components/Header.vue';
	import Explore from './components/Explore.vue';
	export default {
		name: 'App',
		components: {
			NavigationBar,
			Header,
			Explore
		},
	}
</script>

<template>
	<div id="app">
		<NavigationBar />
		<Header />
		<Explore />
	</div>
</template>

<style scoped></style>
