<script>
  export let txt;
  import { fade } from 'svelte/transition';
  let visable = false;
  function startUp(){visable = true;}
</script>
<svelte:window
  on:load={startUp()}
/>
{#each txt as letter,i}
     {#if visable}
      <span class="em" in:fade={{delay: 2000 + i * 50, duration: 0}}>{letter}</span>
     {/if}
{/each}