<script>
  export let url;
  export let id;
  export let text;
  export let icon;
</script>

<article class="Card">
  <img class="Card__image" src={url} alt={id} />
  <button class="Card__button" on:click><i class={icon} /> {text}</button>
</article>

<style>
  .Card {
    width: 280px;
    border-radius: 0.5rem;
    box-shadow: 0 8px 15px var(--black-color);
    transition: 0.3s;
    overflow: hidden;
    background-color: transparent;
  }

  .Card:hover {
    box-shadow: 0 2px 7px var(--med-color);
  }

  .Card__image {
    height: 190px;
    width: 100%;
    object-fit: cover;
  }

  .Card__button {
    width: 100%;
    border: none;
    background-color: transparent;
    transition: 0.3s;
    font-weight: 500;
    color: var(--text-color);
    padding: var(--mb-2) 0;
    font-weight: 600;
  }

  .Card__button:hover {
    cursor: pointer;
    color: var(--main-color);
  }

  @media (min-width: 969px) {
    .Card {
      box-shadow: 0 5px 8px var(--black-color);
    }

    .Card:hover {
      box-shadow: 0 5px 12px var(--med-color);
    }
  }
</style>
