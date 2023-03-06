<script>
	import StatusBar from './StatusBar.svelte';
	export let data;
</script>

<div>
	<h3>
		{data.title}
	</h3>
	<StatusBar statusData={data.status} />
</div>

<style>
	div {
		display: flex;
		align-items: center;
		gap: 0.5rem;
	}
</style>
