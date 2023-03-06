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
  h3 {
    font-size: 2.25rem;
    font-weight: 500;
    margin: 0;
    font-family: myFirstFont;
  }
  div {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
</style>
