<script>
	import StatusBar from '../../../lib/subComponents/StatusBar.svelte';
	import LinkBar from '../../../lib/subComponents/LinkBar.svelte';
	import MoreInfo from '../../../lib/subComponents/MoreInfo.svelte';

	export let data;
	import { cards } from '$lib/data/cardData.json';
	let cardData = cards.filter((cards) => cards.name === data.slug);
	let cardInfo = cardData[0];
</script>

<div class="layout">
	<h1>{cardInfo.name}</h1>
	<StatusBar statusData={cardInfo.status} />
	<p>{cardInfo.description}</p>
	<MoreInfo data={cardInfo} />

	<LinkBar data={cardInfo} status="large" />
</div>

<style>
	.layout {
		display: grid;
		padding-top: 30px;
		padding-left: 20px;
		grid-template-rows: 60px 50px 300px 45px 45px;
		font-size: 0.9rem;
	}
	h1 {
		font-weight: 1000;
		font-family: myFirstFont;
	}
</style>
