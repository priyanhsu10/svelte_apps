<script>
  let name;
  let beltcolor;
  let age;
  const handlesubmit = () => {
    console.log(name, beltcolor, age);
  };
</script>

<form on:submit|preventDefault={handlesubmit}>
  <input type="text" placeholder="name" bind:value={name} /><br />
  <input type="text" placeholder="belt color" bind:value={beltcolor} /><br />
  <input type="number" placeholder="age" bind:value={age} />
  <br />
  <button>submit</button>
</form>

<style>
</style>
