<script>
  // import { getData } from "./components/GetAPI.svelte";

  const URL = "https://api.thecatapi.com/v1/images/search?limit=10";

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
</style>
