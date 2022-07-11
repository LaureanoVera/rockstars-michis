<script>
  import Card from "./Card.svelte";
  import Error from "./Error.svelte";

  export let info;
  export let save;
</script>

<section class="Random">
  {#if !info.error}
    {#each info as item}
      <Card
        on:click={() => save(item.id)}
        url={item.url}
        id={item.id}
        text="Favorites"
        icon="fa-solid fa-circle-plus"
      />
    {/each}
  {:else}
    <Error status={info.status} />
  {/if}
</section>

<style>
  .Random {
    display: grid;
    gap: 2rem 1rem;
    justify-content: center;
    grid-auto-columns: auto;
  }

  @media screen and (min-width: 769px) {
    .Random {
      grid-template-columns: repeat(2, minmax(min-content, 320px));
    }
  }

  @media screen and (min-width: 1024px) {
    .Random {
      grid-template-columns: repeat(3, minmax(min-content, 300px));
    }
  }
</style>
