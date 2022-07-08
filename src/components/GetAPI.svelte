<script context="module">
  export async function getData(urlApi) {
    const response = await fetch(urlApi);
    const data = await response.json();

    return [...data];
  }
</script>
