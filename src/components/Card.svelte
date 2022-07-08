<script>
  export let url;
  export let id;
  export let text;
</script>

<article class="Card">
  <img src={url} alt={id} />
  <button>{text}</button>
</article>

<style>
  .Card {
    max-width: 320px;
    border-radius: 0.25rem;
    box-shadow: 0 0 5px #333;
    overflow: hidden;
  }
  img {
    height: 250px;
    width: 100%;
    object-fit: cover;
  }
</style>
