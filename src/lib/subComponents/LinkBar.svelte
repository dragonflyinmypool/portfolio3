<script>
	export let data;
	export let status;
</script>

<div class="flex-Text">
	{#if status === 'small'}
		<a href={`/detail/${data.name}`} class="link" style="font-size: 20px; line-height: 5px;">+</a>
	{:else}
		<a href={`../`} class="link">-</a>
	{/if}

	{#each Object.entries(data.links) as link}
		<a href={link[1]} class="link">{link[0]}</a>
	{/each}
</div>

<style>
	.flex-Text {
		display: flex;
		flex-direction: row;
		justify-content: flex-start;
		gap: 0.8rem;
		padding-top: 0.5rem;
		font-size: small;
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
