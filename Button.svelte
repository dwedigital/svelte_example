<script>
	import { onMount } from "svelte";
	let count = localStorage.getItem("count");
	export let name;
	onMount(() => {
	  if (localStorage.getItem("count")) {
	    count = localStorage.getItem("count");
	  } else {
	    localStorage.setItem("count", 0);
	  }
	});
	function handleClick() {
	  count = parseInt(localStorage.getItem("count"), 10);
	  const newCount = (count += 1);
	  localStorage.setItem("count", newCount);
	}
</script>

<style>
</style>

<button on:click={handleClick} class="mt-4 mb-2 btn btn-primary">
{#if name} {name} c{:else}C{/if}licked {count} {count === 1 ? 'time' : 'times'}
</button>
<p><button on:click="{()=>{localStorage.setItem("count", 0); count=0}}" class="btn btn-danger">Clear count</button></p>