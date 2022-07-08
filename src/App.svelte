<script>
  import Random from "./components/Random.svelte";
  import Favorites from "./components/Favorites.svelte";
  import Card from "./components/Card.svelte";
  import Error from "./components/Error.svelte";

  const API_KEY = "ef968935-d84f-4d9a-a4ef-d1e80b715d94";
  const URL_RAN = `https://api.thecatapi.com/v1/images/search?limit=10&api_key=${API_KEY}`;
  const URL_FAV = `https://api.thecatapi.com/v1/favourites?limit=5&api_key=${API_KEY}`;

  let info = [];
  let favList = [];

  const loadRandom = async () => {
    const res = await fetch(URL_RAN);
    const data = await res.json();

    if (res.status !== 200) {
      info = { status: res.status, msg: data.message, error: true };
    } else {
      info = [...data];
    }
  };

  const loadFavorites = async () => {
    const res = await fetch(URL_FAV);
    const data = await res.json();

    if (res.status !== 200) {
      favList = { status: res.status, msg: data.message, error: true };
    } else {
      console.log(data);
    }
  };

  loadRandom();
  loadFavorites();
</script>

<main>
  <h1>Michis App</h1>
  <Random>
    {#if !info.error}
      {#each info as item}
        <Card url={item.url} id={item.id} text="Favorites" />
      {/each}
    {:else}
      <Error status={info.status} />
    {/if}
  </Random>

  {#if !favList.error}
    <Favorites />
  {:else}
    <Error status={favList.status} message={favList.msg} />
  {/if}

  <button on:click={loadRandom}>Refresh</button>
</main>

<style>
  :global(h1, h2, h3) {
    text-align: center;
  }
</style>
