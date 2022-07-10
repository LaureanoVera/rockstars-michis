<section class="Random">
  <slot />
</section>

<style>
  .Random {
    display: grid;
    gap: 1rem;
    justify-content: center;
  }

  @media screen and (min-width: 769px) {
    .Random {
      grid-template-columns: repeat(3, minmax(min-content, 300px));
    }
  }
</style>
