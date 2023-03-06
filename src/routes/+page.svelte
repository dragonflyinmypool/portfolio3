<script>
	// Components
	import ProjectCard from '$lib/ProjectCard.svelte';
	import Header from '$lib/infoCards/Header.svelte';
	import CourseCard from '$lib/infoCards/CourseCard.svelte';

	// Project Cards Data
	import { cards } from '$lib/data/cardData.json';
</script>

<main>
	<Header />
	<div class="grid">
		{#each cards as data}
			<ProjectCard {data} />
		{/each}
		<CourseCard />
	</div>
</main>

<style>
	main {
		/* Set the max width, and center content */
		max-width: 1200px;
		margin: auto;
	}
	.grid {
		/* Make a grid */
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(325px, 1fr));
		gap: 1rem;
	}
</style>
