<script>
	import { courses } from '$lib/data/courses.json';
	const sortedCourses = courses.sort((a, b) => {
		if (a.status === 'Not yet started' && b.status !== 'Not yet started') {
			return -1;
		} else if (a.status !== 'Not yet started' && b.status === 'Not yet started') {
			return 1;
		} else if (a.status === 'Taking currently' && b.status !== 'Taking currently') {
			return -1;
		} else if (a.status !== 'Taking currently' && b.status === 'Taking currently') {
			return 1;
		} else if (a.status === 'Completed' && b.status !== 'Completed') {
			return -1;
		} else if (a.status !== 'Completed' && b.status === 'Completed') {
			return 1;
		} else {
			return 0;
		}
	});
</script>

<div class="page">
	<h2>Courses</h2>
	<div class="key">
		<div class="completed">Completed</div>
		<div class="taking">Taking currently</div>
		<div class="notStarted">Not yet started</div>
	</div>
	<div class="grid">
		{#each courses as course}
			{#if course.status === 'Completed'}
				<div class="completed row">
					<p>{course.title}</p>
					<span>{course.institution}</span>
				</div>
			{:else if course.status === 'Taking currently'}
				<div class="taking row">
					<p>{course.title}</p>
					<span>{course.institution}</span>
				</div>
			{:else if course.status === 'Not yet started'}
				<div class="notStarted row">
					<p>{course.title}</p>
					<span>{course.institution}</span>
				</div>
			{/if}
		{/each}
	</div>

	<div class="flex-Text">
		<a href={`../`} class="link">-</a>
	</div>
</div>

<style>
	.page {
		background-color: #dadedb;
		padding: 20px;
		border-radius: 15px;
	}
	h2 {
		margin-bottom: 20px;
	}
	.key {
		display: flex;
		justify-content: flex-start;
		gap: 0.3rem;
		color: #dadedb;
		margin-bottom: 20px;
	}
	.key > * {
		padding: 0.1rem 0.5rem;
		border-radius: 5px;
	}
	.grid {
		display: grid;
		grid-gap: 0.1rem;
		background-color: #dadedb;
		grid-template-columns: minmax(80px, 650px);
		max-width: 900px;
		border-radius: 15px;
		color: white;
	}
	.grid > * {
		background-color: var(--card-background);
		padding: 0.6rem 0.5rem;
		border-radius: 5px;
	}
	/* green border */
	.completed {
		background-color: #358238;
	}

	/* grey border */
	.taking {
		background-color: rgb(133, 174, 117);
	}
	.notStarted {
		background-color: #a9a9a9;
	}
	span {
		font-size: 0.6rem;
	}

	.flex-Text {
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		gap: 0.8rem;
		padding-top: 0.5rem;
		font-size: 20px;
		height: 32px;
	}
	.link {
		background-color: #e6efea;
		padding: 0.6rem 0.5rem;
		line-height: 4px;
	}

	a {
		color: var(--title-color);
		font-family: myFirstFont;
		text-decoration: none;
		font-weight: bold;
		border-radius: 10px;
		line-height: 12px;
	}
</style>
