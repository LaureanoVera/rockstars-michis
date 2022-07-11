<footer class="Footer">
  <p>&copy;Laureano Vera 2022</p>
  <ul class="Footer__links">
    <li>
      <a
        href="https://www.linkedin.com/in/laureano-vera-320086204/"
        target="_blank"
        class="Footer__link"><i class="fa-brands fa-linkedin-in" /></a
      >
    </li>
    <li>
      <a
        href="https://github.com/LaureanoVera"
        target="_blank"
        class="Footer__link"><i class="fa-brands fa-github-alt" /></a
      >
    </li>
    <li>
      <a
        href="https://laureanovera.netlify.app/"
        target="_blank"
        class="Footer__link"><i class="fa-solid fa-code" /></a
      >
    </li>
  </ul>
</footer>

<style>
  .Footer {
    box-shadow: 0 -1px 8px var(--black-color);
    background-color: rgba(255, 255, 255, 0.03);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);
    min-height: 120px;
    border-radius: 0 var(--mb-4) 0 0;
    display: grid;
    justify-content: space-around;
    align-items: center;
  }

  .Footer p {
    color: var(--main-color);
  }

  .Footer__links {
    display: flex;
    justify-content: space-around;
  }

  .Footer__links li {
    list-style: none;
  }

  .Footer__link {
    color: var(--text-color);
    transition: 0.3s;
    font-size: 1.25rem;
  }

  .Footer__link:hover {
    text-shadow: 2px 2px 4px var(--main-color);
    color: var(--black-color);
  }

  @media (min-width: 769px) {
    .Footer {
      display: flex;
      align-items: center;
    }

    .Footer__links {
      width: 40%;
      max-width: 440px;
    }
  }
</style>
