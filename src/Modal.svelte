<script>
  export let message;
  export let list = [];
  const localtogle = () => {
    console.log("togel called");
    console.log(typeof togle);
    togle();
  };
  export let togle;
  export let showModel = false;
  let ispromo = false;
</script>

{#if showModel}
  <div class="backdrop" class:promo={ispromo}>
    <div class="model">
      <!-- <p>Sign upd for the offer</p>
      <p>{message}</p>
      <ul>
        {#each list as item (item.id)}
          <li>{item.name} ,{item.age}</li>
        {/each}
      </ul> -->
      <slot />
      <!-- <button on:click={localtogle}> close</button> -->
    </div>
  </div>
{/if}

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.8);
  }
  .model {
    background: white;
    width: 400px;
    margin: 10% auto;
    height: auto;
    text-align: center;
    border-radius: 1rem;
  }
  .promo .model {
    background: crimson;
    color: white;
  }
</style>
