<script>
  export let url;
  export let id;
  export let text;
</script>

<article class="Card">
  <img src={url} alt={id} />
  <button on:click>{text}</button>
</article>

<style>
  .Card {
    width: 280px;
    border-radius: 0.5rem;
    box-shadow: 0 0 3px var(--text-color);
    transition: 0.3s;
    overflow: hidden;
    background-color: transparent;
  }

  .Card:hover {
    box-shadow: 0 0 10px var(--main-color);
  }

  img {
    height: 190px;
    width: 100%;
    object-fit: cover;
  }

  button {
    width: 100%;
    border: none;
    background-color: transparent;
    transition: 0.3s;
    font-weight: 500;
    color: var(--text-color);
  }

  button:hover {
    cursor: pointer;
    color: var(--main-color);
  }
</style>
