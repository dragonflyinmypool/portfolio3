<script>
	// import genericCard.svelte
	import GenericCard from '../GenericCard.svelte';
</script>

<GenericCard>
	<ul>
		<li>London 1990</li>
	</ul>
	<ul>
		<li>HTML, CSS, Javascript, Svelte, Node</li>
		<li>Accounting fundementals</li>
		<li>Principals of design</li>
	</ul>
	<ul>
		<li>🥇FAU Architecture Design Competition</li>
		<li>🥈MIT Miami Healthcare Hackathon</li>
	</ul>
</GenericCard>

<style>
	ul {
		margin-top: 20px;
		list-style: none;
	}
</style>
