<script>
  export let data;

  import GenericCard from './GenericCard.svelte';
  import LinkBar from './subComponents/LinkBar.svelte';
  import CardTitle from './subComponents/CardTitle.svelte';
  import MoreInfo from './subComponents/MoreInfo.svelte';
  import StatusBar from './subComponents/StatusBar.svelte';
</script>

<GenericCard>
  <div class="layout">
    <CardTitle {data} />
    <StatusBar statusData={data} />
    <MoreInfo {data} />
    <p>{data.description}</p>
    <LinkBar {data} status="small" />
  </div>
</GenericCard>

<style>
  .layout {
    display: grid;
    grid-template-rows: 45px 15px 30px 100px 35px;
    font-size: 0.9rem;
  }
</style>
