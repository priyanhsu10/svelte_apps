<script>
  import Model from "./Modal.svelte";
  import AddPersonform from "./AddPersonform.svelte";
  import Modal from "./Modal.svelte";
  import Todo from "./Todo.svelte";
  let firstname = "priyanshu";
  let lastname = "parate";
  let showModel = false;
  let toggle = false;
  let color = "black";
  const togle = () => (showModel = !showModel);
  $: fullname = `${firstname}  ${lastname}`;
  $: {
    console.log(firstname);
    console.log(lastname);
  }
  const handleClick = () => {
    if (toggle) {
      color = "orrange";
    } else {
      color = "black";
    }
    toggle = !toggle;
  };
  const handleInput = (e) => {
    color = e.target.value;
  };

  let people = [
    { name: "yoshi", beltColour: "black", age: 25, id: 1 },
    { name: "mario", beltColour: "orange", age: 45, id: 2 },
    { name: "luigi", beltColour: "brown", age: 35, id: 3 },
  ];
  const handleClick1 = (id) => {
    people = people.filter((x) => x.id != id);
  };
  let num = 6;
</script>

<main class="main">
  <button on:click={togle}>show </button>
  <h4>Hello {fullname}</h4>
  <Todo />
  <!-- <Model
    message="hi this message form message"
    list={people}
    {showModel}
    {togle}
  >
    <h4>add new person</h4>
    first name
    <input type="text" bind:value={firstname} />
    last name
    <input type="text" bind:value={lastname} />

    <button on:click={handleClick}>change</button>
  </Model> -->
  <!-- <Model {showModel}>
    <AddPersonform />
  </Model> -->
  <!-- <input type="text" on:input={handleInput} value={color} /> -->

  <!-- {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      <p>{person.age} year old ,{person.beltColour}</p>
      <button on:click={() => handleClick1(person.id)}>delete</button>
    </div>
  {:else}
    <p>there is no data</p>
    <p>there is no data</p>
    <p>there is no data</p>
  {/each}

  {#if num > 20}
    <p>number is greater than 20</p>
  {:else if num > 5}
    <p>greater than 5</p>
  {:else}
    <p>Not greater than 5</p>
  {/if} -->
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
