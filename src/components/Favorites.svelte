<section class="Favorites">
  <h2>Favorites</h2>
  <article class="Favorites__container">
    <slot />
  </article>
</section>

<style>
  .Favorites {
    text-align: center;
    margin: var(--mb-4) 0;
  }

  .Favorites__container {
    display: grid;
    gap: 1rem;
    justify-content: center;
  }

  @media screen and (min-width: 769px) {
    .Favorites__container {
      grid-template-columns: repeat(3, minmax(min-content, 300px));
    }
  }
</style>
