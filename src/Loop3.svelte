<script>
  let people = [
    { name: "yoshi", beltColor: "black", age: 25, id: 1 },
    { name: "jhon", beltColor: "ornage", age: 45, id: 2 },
    { name: "mari", beltColor: "blue", age: 55, id: 3 },
  ];
</script>

<main>
  <!--	<div>
		<h4>{people[0].name}</h4>
		<p>{people[0].beltColor}</p>
	</div> -->

  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      <p>{person.age} years old, {person.beltColor} belt.</p>
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
