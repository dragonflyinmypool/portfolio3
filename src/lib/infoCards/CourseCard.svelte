<script>
	// import genericCard.svelte
	import GenericCard from '../GenericCard.svelte';
	import { courses } from '$lib/data/courses.json';
	console.log(courses);
	// filter only courses that course.status is 'Completed'
	const completedCourses = courses.filter((course) => course.status === 'Completed');
	console.log(completedCourses);
</script>

<GenericCard>
	<div class="layout">
		<h3>Courses</h3>
		<ul>
			{#each completedCourses as course}
				<li>
					{course.title}
					({course.institution})
				</li>
			{/each}
			<div />
		</ul>
		<div class="flex-Text">
			<a href={`./courses`} class="link">+</a>
		</div>
	</div>
</GenericCard>

<style>
	.layout {
		display: grid;
		grid-template-rows: 45px 150px 35px;
	}
	ul {
		list-style: none;
		font-size: 10px;
	}
	li {
		padding: 0.05rem 0;
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
	a:hover {
		color: purple;
	}
</style>
