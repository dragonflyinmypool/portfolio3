<script>
	export let statusData;
</script>

<div class="status">
	{#if 'status' in statusData}
		<span>{statusData.status}</span>
	{/if}
	{#if 'version' in statusData}
		<span>V{statusData.version}</span>
	{/if}
</div>

<style>
	span {
		font-size: 0.7rem;
		padding-right: 0.5rem;
		border: 2px solid #e6efea;
		border-radius: 0.5rem;
		color: #f0fff6;
		padding: 2px 10px;
	}
</style>
