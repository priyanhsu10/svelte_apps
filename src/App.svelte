<script>
  //   let firstname = "priyanshu";
  //   let lastname = "parate";
  //   $: fullname = `${firstname}  ${lastname}`;
  //   $: {
  //     console.log(firstname);
  //     console.log(lastname);
  //   }
  //   const handleClick = () => {
  //     if (toggle) {
  //       color = "orrange";
  //     } else {
  //       color = "black";
  //     }
  //     toggle = !toggle;
  //   };
  //   const handleInput = (e) => {
  //     color = e.target.value;
  //   };
  //   loops

  let people = [
    { name: "yoshi", beltColour: "black", age: 25, id: 1 },
    { name: "mario", beltColour: "orange", age: 45, id: 2 },
    { name: "luigi", beltColour: "brown", age: 35, id: 3 },
  ];
  const handleClick = (id) => {
    people = people.filter((x) => x.id != id);
  };
</script>

<main>
  <!-- <h1>Hello {fullname}</h1>
  first name
  <input type="text" bind:value={firstname} />
  last name
  <input type="text" bind:value={lastname} />

  <button on:click={handleClick}>change</button> -->
  <!-- <input type="text" on:input={handleInput} value={color} /> -->

  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      <p>{person.age} year old ,{person.beltColour}</p>
      <button on:click={() => handleClick(person.id)}>delete</button>
    </div>
  {:else}
    <p>there is no data</p>
    <p>there is no data</p>
    <p>there is no data</p>
  {/each}
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
