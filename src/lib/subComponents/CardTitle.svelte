<script>
  export let data;
  console.log(data);
</script>

<div>
  <h3>
    {data.title}
  </h3>
</div>

<style>
  h3 {
    font-size: 1.6rem;
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
