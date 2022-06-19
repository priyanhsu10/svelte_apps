<script>
  let items = [];
  let item;

  const add = () => {
    items = [item, ...items];
  };
  const remove = (i) => {
    items = items.filter((x) => x != x);
  };
</script>

<div>
  <form on:submit|preventDefault={add}>
    <input type="text" bind:value={item} />
    <button>add</button>
  </form>
  {#each items as i, index (index)}
    <div class="item" on:click={remove}>{i}</div>
  {/each}
</div>

<style>
  .item {
    background: gray;
    cursor: pointer;
    width: 100%;
    margin: 2rem;
  }
</style>
