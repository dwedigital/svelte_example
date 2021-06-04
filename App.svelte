<script>
  import Button from "./Button.svelte";
  import Chuck from "./Chuck.svelte";
  import Country from "./Country";
  let name;
</script>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
</style>

<main>
	<h1>Svelte Example</h1>
<div>
  <label for="name">Name: </label>
  <input type="text" bind:value={name} name="name">
</div>
	<Button name="{name}"/>
  <Chuck/>
  <Country />
</main>