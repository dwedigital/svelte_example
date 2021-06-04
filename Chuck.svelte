<script>
  import { onMount } from "svelte";
  let joke;
  onMount(() => {
    getJoke();
  });

  function getJoke() {
    fetch("https://api.chucknorris.io/jokes/random")
      .then(data => data.json())
      .then(data => (joke = data.value));
  }
</script>

<p>{joke}</p>

<button on:click="{getJoke}" class ="btn btn-secondary mb-4">Hit me</button>