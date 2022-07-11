<script>
  import Card from "./Card.svelte";
  import Error from "./Error.svelte";

  export let favList;
  export let deleteFav;
</script>

<section class="Favorites">
  <h2 class="Favorites__title">Favorites</h2>
  <article class="Favorites__container">
    {#if !favList.error}
      {#each favList as item}
        <Card
          on:click={() => deleteFav(item.id)}
          url={item.image.url}
          id={item.image.id}
          text="Delete"
          icon="fa-solid fa-circle-minus"
        />
      {/each}
    {:else}
      <Error status={favList.status} message={favList.msg} />
    {/if}
  </article>
</section>

<style>
  .Favorites {
    text-align: center;
    margin: calc(var(--mb-4) * 2.5) 0 var(--mb-4);
    min-height: 70vh;
    padding: var(--mb-4) 0;
  }

  .Favorites__title {
    position: relative;
    color: var(--main-color);
    margin: var(--mb-4) 0;
    text-align: center;
    text-transform: uppercase;
    font-weight: 700;
  }

  .Favorites__title::after {
    position: absolute;
    content: "";
    width: 2.35rem;
    height: 0.18rem;
    left: 0;
    right: 20%;
    margin: 0 auto;
    top: 2.4rem;
    background-color: var(--text-color);
  }

  .Favorites__container {
    display: grid;
    gap: 1rem;
    justify-content: center;
  }

  @media screen and (min-width: 769px) {
    .Favorites__container {
      grid-template-columns: repeat(2, minmax(min-content, 320px));
    }

    .Favorites__title::after {
      right: 10%;
    }
  }

  @media screen and (min-width: 1024px) {
    .Favorites__container {
      grid-template-columns: repeat(3, minmax(min-content, 300px));
    }

    .Favorites__title::after {
      right: 5%;
    }
  }
</style>
