<script>
import GitHubCard from './Socials/GitHubCard.vue'
import NpmCard from './Socials/NpmCard.vue';
import XCard from './Socials/XCard.vue'
export default {
	name: 'Socials',
	components: { GitHubCard, XCard, NpmCard },
}
</script>

<template>
	<div class="socials">
		<XCard />
		<NpmCard />
		<GitHubCard />
	</div>
</template>

<style scoped>
	.socials {
		width: 100%;
		min-height: 50vh;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
	}

	.socials > * {
		width: 500px;
		margin: 1rem;
	}
	
	@media (max-width: 768px) {
		.socials {
			margin-top: 10rem;
		}
	}
</style>