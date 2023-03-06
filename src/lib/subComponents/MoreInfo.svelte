<script>
  import StatusBar from './StatusBar.svelte';
  export let data;
</script>

<div class="small-text">
  <div class="flex-Text small-text">
    {#if 'stack' in data}
      {#each data.stack as tech}
        <div class="tech">{tech}</div>
      {/each}
    {/if}
    {#if 'usageStats' in data}
      <div class="tech">{data.usageStats.stars}</div>
      <div class="tech">{data.usageStats.reviews}</div>
    {/if}
    <StatusBar statusData={data.status} />
  </div>
</div>

<style>
  .flex-Text {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    flex-wrap: wrap;
    gap: 0.5rem;
  }
  .tech {
    line-height: 1rem;
  }

  .small-text {
    font-size: 0.7rem;
  }
</style>
