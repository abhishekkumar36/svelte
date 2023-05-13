<script>
  let people = [
    { name: "Rahul", beltColor: "black", age: 25, id: 1 },
    { name: "Abhishek", beltColor: "yellow", age: 25, id: 2 },
    { name: "Gunjan", beltColor: "brown", age: 25, id: 3 },
  ];
  const handleClick = (id) => {
    people = people.filter((person) => person.id != id);
  };
</script>

<main>
  {#each people as person (person.id)}
    <div>
      <h4>{person.name}</h4>
      <p>{person.age} years old, {person.beltColor} belt</p>
      <button on:click={() => handleClick(person.id)}>delete</button>
    </div>
  {:else}
    <p>There is nothing to show</p>
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
