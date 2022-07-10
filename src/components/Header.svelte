<header class="Header">
  <ul class="Header__nav">
    <li class="Header__item">
      <button on:click><i class="fa-solid fa-arrow-rotate-right" /></button> refresh
    </li>
  </ul>
</header>

<style>
  .Header {
    background-color: var(--med-color);
    padding: var(--mb-2) 0;
    margin-bottom: var(--mb-4);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
  }

  .Header__nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .Header__item {
    list-style: none;
    border: none;
    background-color: transparent;
    font-size: 1.2rem;
    color: var(--text-color);
  }

  .Header__item button {
    border: none;
    background-color: var(--dark-color);
    border-radius: 50%;
    width: 36px;
    height: 36px;
    font-size: 1.15rem;
    color: var(--main-color);
    box-shadow: 0 0 2px var(--main-color);
  }

  .Header__item button:hover {
    cursor: pointer;
    transform: rotate(360deg);
    transition: 0.35s;
  }
</style>
