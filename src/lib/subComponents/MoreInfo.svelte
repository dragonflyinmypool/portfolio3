<script>
	export let data;
</script>

<div class="small-text">
	<div class="flex-Text small-text">
		{#if 'usageStats' in data}
			<div class="tech">{data.usageStats.stars}</div>
			<div class="tech">{data.usageStats.reviews}</div>
		{/if}
	</div>
	<div class="flex-Text">
		{#if 'stack' in data}
			{#each data.stack as tech}
				<div class="tech">{tech}</div>
			{/each}
		{/if}
	</div>
</div>

<style>
	.flex-Text {
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		flex-wrap: wrap;
		gap: 0.5rem;
		padding-top: 0.5rem;
	}
	.tech {
		line-height: 1rem;
	}

	.small-text {
		font-size: 0.7rem;
	}
</style>
