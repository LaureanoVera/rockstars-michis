<script>
  // import { getData } from "./components/GetAPI.svelte";

  const API_KEY = "ef968935-d84f-4d9a-a4ef-d1e80b715d94";
  const URL = `https://api.thecatapi.com/v1/images/search?limit=10&api_key=${API_KEY}`;

  let info = [];

  const getData = async () => {
    const res = await fetch(URL);
    const data = await res.json();

    info = [...data];
  };

  getData();
</script>

<main>
  <section>
    {#each info as item}
      <article>
        <img src={item.url} alt={item.id} />
        <h3>User: {item.id}</h3>
      </article>
    {/each}
  </section>
  <button on:click={getData}>Refresh</button>
</main>

<style>
  img {
    height: 250px;
    width: 250px;
    object-fit: cover;
  }

  h3 {
    margin-top: 0;
  }
</style>
