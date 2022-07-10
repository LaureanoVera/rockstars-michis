<header class="Header">
  <ul class="Header__nav">
    <li class="Header__item">
      <button on:click><i class="fa-solid fa-arrow-rotate-right" /></button>
    </li>
  </ul>
</header>

<style>
  .Header {
    margin-bottom: var(--mb-4);
    backdrop-filter: blur(5px);
    -webkit-backdrop-filter: blur(5px);
    background-color: rgba(255, 255, 255, 0.06);
    width: 100%;
    backdrop-filter: blur(10px);
    border-radius: 0 0 var(--mb-3) var(--mb-3);
    padding: var(--mb-4);
    box-shadow: 0 4px 8px var(--black-color);
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
    color: var(--text-color);
    font-size: 1.2rem;
  }

  .Header__item button {
    display: inline-block;
    border: none;
    border-radius: var(--mb-2);
    width: 60px;
    height: 40px;
    font-size: 1.15rem;
    box-shadow: 0 0 8px var(--black-color);
    background-color: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(30px);
    color: var(--main-color);
  }

  .Header__item button:hover {
    cursor: pointer;
    transform: rotate(360deg);
    transition: 0.35s;
    box-shadow: 0 0 8px var(--med-color);
  }

  @media (min-width: 769px) {
    .Header__item button {
      border-radius: var(--mb-2);
      width: 70px;
      height: 45px;
    }
  }
</style>
