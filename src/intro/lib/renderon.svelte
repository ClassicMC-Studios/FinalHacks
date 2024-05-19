<script>
  export let txt,s;
  import { fade } from 'svelte/transition';
  export let visable = false;
</script>
{#each txt as letter,i}
     {#if visable}
      <span in:fade={{delay: s + i * 50, duration: 0}}>{letter}</span>
     {/if}
{/each}