<script>
  export let statusData;
</script>

<div class="status">
  {#if 'status' in statusData}
    <span>Status: {statusData.status}</span>
  {/if}
  {#if 'version' in statusData}
    <!-- <span>V{statusData.version}</span> -->
  {/if}
</div>

<style>
  .status {
    font-size: 0.7rem;
  }
</style>
