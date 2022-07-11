<footer class="Footer">
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
  <p>&copy;Laureano Vera 2022</p>
</footer>

<style>
  .Footer {
    box-shadow: 0 0 8px var(--med-color);
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
    font-weight: 700;
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
    font-size: 1.5rem;
  }

  .Footer__link:hover {
    text-shadow: 0 0 5px var(--main-color);
    color: var(--black-color);
  }

  @media (min-width: 769px) {
    .Footer {
      display: flex;
      flex-direction: row-reverse;
      align-items: center;
    }

    .Footer__links {
      width: 40%;
      max-width: 440px;
    }
  }
</style>
