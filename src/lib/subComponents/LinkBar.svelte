<script>
  export let data;
  export let status;
</script>

<div class="flex-Text">
  {#if status === 'small'}
    <a href={`/detail/${data.name}`} class="link" style="font-size: 15px;">+</a>
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
    /* background-color: #dddddd; */
    padding: 0.6rem 0.5rem;
    line-height: 2px;
  }

  a {
    color: black;
    font-family: sans-serif;
    text-decoration: none;
    font-size: 0.7rem;
    padding-right: 0.5rem;
    border: 1px solid black;
    border-radius: 0.5rem;
    padding: 2px 10px;
  }
  a:hover {
    color: var(--card-background);
    background: white;
    border: 1px solid white;
  }
</style>
