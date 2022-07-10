<section class="Random">
  <slot />
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
