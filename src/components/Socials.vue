<script lang="ts">
import GitHubCard from './Socials/GitHubCard.vue'
import XCard from './Socials/XCard.vue'
export default {
	name: 'Socials',
	components: { GitHubCard, XCard },
}
</script>

<template>
	<div class="socials">
		<XCard borderGradient="linear-gradient(110deg, #34343494, #b9b9b9c5)" />
		<GitHubCard borderGradient="linear-gradient(110deg, #fafafa, #6cc644)" />
	</div>
</template>

<style scoped>
	.socials {
		width: 100%;
		height: 50vh;
		display: flex;
		justify-content: center;
		flex-wrap: wrap;
	}

	.socials > * {
		margin: 1rem;
	}
	
	@media (max-width: 768px) {
		.socials {
			margin-top: 10rem;
		}
	}
</style>