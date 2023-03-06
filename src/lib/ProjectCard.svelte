<script>
	export let data;

	import GenericCard from './GenericCard.svelte';
	import LinkBar from './subComponents/LinkBar.svelte';
	import CardTitle from './subComponents/CardTitle.svelte';
	import MoreInfo from './subComponents/MoreInfo.svelte';
</script>

<GenericCard>
	<div class="layout">
		<CardTitle {data} />
		<p>{data.description}</p>
		<MoreInfo {data} />
		<LinkBar {data} status="small" />
	</div>
</GenericCard>

<style>
	.layout {
		display: grid;
		grid-template-rows: 45px 100px 50px 35px;
		font-size: 0.9rem;
	}
</style>
