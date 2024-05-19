<script>
	import { onMount, onDestroy } from 'svelte';
	import { slide } from 'svelte/transition';
	
	let greetings = ['↓', '↓', '↓'];
	let index = 0;
	let roller;
	
	onMount(() => {
		roller = setInterval(() => {
			if (index === greetings.length - 1) index = 0;
			else index++;
		}, 1250);
	});
	
	onDestroy(() => {
		clearInterval(roller);
	});
</script>
<style>
  h1{
    position:absolute;
    left:50%;
    transform: translate(-50%);
		font-weight:bolder;
  }
</style>

{#key index}
	<h1 transition:slide>{greetings[index]}</h1>
{/key}