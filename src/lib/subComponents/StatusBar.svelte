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
</style>
