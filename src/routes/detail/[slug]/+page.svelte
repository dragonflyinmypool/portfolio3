<script>
  import StatusBar from '../../../lib/subComponents/StatusBar.svelte';
  import LinkBar from '../../../lib/subComponents/LinkBar.svelte';
  import MoreInfo from '../../../lib/subComponents/MoreInfo.svelte';

  export let data;
  import { projects } from '$lib/data/cardData.json';
  let cardData = projects.filter((projects) => projects.name === data.slug);
  let cardInfo = cardData[0];

  console.log(data);
</script>

<div class="layout">
  <h1>{cardInfo.name}</h1>
  <StatusBar statusData={cardInfo} />
  <MoreInfo data={cardInfo} />

  <p>{cardInfo.description}</p>

  <LinkBar data={cardInfo} status="large" />
</div>

<style>
  .layout {
    display: grid;
    padding-top: 30px;
    padding-left: 20px;
    grid-template-rows: 60px 30px 30px 300px 45px;
    font-size: 0.9rem;
  }
  h1 {
    font-weight: 1000;
    font-family: myFirstFont;
  }
  img {
    max-width: 100%;
    max-height: 100%;
    padding: 20px;
  }
</style>
