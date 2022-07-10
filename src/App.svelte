<script>
  import Header from "./components/Header.svelte";
  import Random from "./components/Random.svelte";
  import Favorites from "./components/Favorites.svelte";
  import Card from "./components/Card.svelte";
  import Error from "./components/Error.svelte";

  const API_KEY = "ef968935-d84f-4d9a-a4ef-d1e80b715d94";
  const URL_RAN = `https://api.thecatapi.com/v1/images/search?limit=12&api_key=${API_KEY}`;
  const URL_FAV = `https://api.thecatapi.com/v1/favourites?limit=6&api_key=${API_KEY}`;

  let info = [];
  let favList = [];
  let saveFav = [];

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
      console.log("LOAD FAV");
      console.log(data);
      favList = [...data];
    }
  };

  const saveFavorites = async () => {
    const res = await fetch(URL_FAV, {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ image_id: "dje" }),
    });
    const data = await res.json();

    console.log("SAVE");
    console.log(data);

    if (res.status !== 200) {
      saveFav = { status: res.status, msg: data.message, error: true };
    }
  };

  loadRandom();
  loadFavorites();
  saveFavorites();
</script>

<main>
  <Header on:click={loadRandom} />
  <Random>
    {#if !info.error}
      {#each info as item}
        <Card
          on:click={saveFavorites}
          url={item.url}
          id={item.id}
          text="Favorites"
        />
      {/each}
    {:else}
      <Error status={info.status} />
    {/if}
  </Random>

  {#if saveFav.error}
    <Error status={saveFav.status} message={saveFav.msg} />
  {/if}

  <Favorites>
    {#if !favList.error}
      {#each favList as item}
        <Card url={item.image.url} id={item.image.id} text="Delete" />
      {/each}
    {:else}
      <Error status={favList.status} message={favList.msg} />
    {/if}
  </Favorites>
</main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600&display=swap");

  :global(:root) {
    --main-color: #64ffcc;
    --med-color: #64ffcc64;
    --text-color: #959a9d;
    --dark-color: #262a2d;

    --mb-1: 0.25rem;
    --mb-2: 0.5rem;
    --mb-3: 0.75rem;
    --mb-4: 1rem;

    --gradient: linear-gradient(180deg, #64ffcc49 10%, #262a2d44 100%);
  }

  :global(*) {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: "Montserrat", sans-serif;
  }

  :global(h1, h2, h3) {
    text-align: center;
  }

  :global(body) {
    background-color: #0d0d0d;
  }

  :global(h2) {
    font-size: 2rem;
  }
</style>
