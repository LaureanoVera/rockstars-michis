<script>
  import Header from "./components/Header.svelte";
  import Random from "./components/Random.svelte";
  import Favorites from "./components/Favorites.svelte";
  import Card from "./components/Card.svelte";
  import Error from "./components/Error.svelte";
  import Loading from "./components/Loading.svelte";
  import Footer from "./components/Footer.svelte";

  const API_KEY = "ef968935-d84f-4d9a-a4ef-d1e80b715d94";
  const URL_RAN = `https://api.thecatapi.com/v1/images/search?limit=12&api_key=${API_KEY}`;
  const URL_FAV = `https://api.thecatapi.com/v1/favourites?&api_key=${API_KEY}`;

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
      favList = [...data];
    }
  };

  const saveFavorites = async (catID) => {
    const res = await fetch(URL_FAV, {
      method: "POST",
      headers: {
        "x-api-key": API_KEY,
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ image_id: String(catID) }),
    });
    const data = await res.json();

    if (res.status !== 200) {
      saveFav = { status: res.status, msg: data.message, error: true };
    } else {
      loadFavorites();
    }
  };

  const deleteFavorites = async (id) => {
    const res = await fetch(
      `https://api.thecatapi.com/v1/favourites/${id}?&api_key=${API_KEY}`,
      {
        method: "DELETE",
      }
    );
    const data = await res.json();

    if (res.status !== 200) {
      favList = { status: res.status, msg: data.message, error: true };
    } else {
      loadFavorites();
    }
  };

  // loadRandom();
  loadFavorites();
</script>

<Header on:click={loadRandom} />
<main>
  {#if info.length <= 0}
    <Loading />
  {:else}
    <Random save={saveFavorites} {info} />
  {/if}

  <Favorites deleteFav={deleteFavorites} {favList} />
</main>
<Footer />

<style>
  @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600&display=swap");

  :global(:root) {
    --main-color: #64ffcc;
    --med-color: rgba(102, 255, 204, 0.392);
    --text-color: #879296;
    --dark-color: #4f5457;
    --black-color: #000;

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
