<script>
  import Modal from "./components/Model.svelte";

  let people = [
    { name: "yoshi", beltColor: "black", age: 25, id: 1 },
    { name: "jhon", beltColor: "ornage", age: 45, id: 2 },
    { name: "mari", beltColor: "brown", age: 55, id: 3 },
  ];

  const handleClick = (id) => {
    people = people.filter((person) => person.id != id);
  };
</script>

<Modal message="Hey, i am a prop value" isPromo={true} />
<main>
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      {#if person.beltColor === "black"}
        <p><strong> MASTER NINJA</strong></p>
      {/if}
      <p>{person.age} years old, {person.beltColor} belt.</p>
      <button on:click={() => handleClick(person.id)}> delete</button>
    </div>
  {:else}
    <p>There are no people to show...</p>
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
