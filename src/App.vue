<script>
	import NavigationBar from './components/NavigationBar.vue';
	import Header from './components/Header.vue';
	import Explore from './components/Explore.vue';
	import Socials from './components/Socials.vue';
	// import Form from './components/Form.vue';
	export default {
		name: 'App',
		components: {
			NavigationBar,
			Header,
			Explore,
			Socials,
			// Form,
		},
	}
</script>

<template>
	<div id="app">
		<NavigationBar />
		<Header />
		<Explore />
		<Socials />
		<!-- <Form /> -->
	</div>
</template>

<style scoped></style>
