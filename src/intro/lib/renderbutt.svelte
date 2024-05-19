<script>
  export let s;
  import { fade } from 'svelte/transition';
  export let visable = false;
</script>
<style>
  button{
    background-color: hsla(0, 0%, 27%, 0);
    border-radius: 0;
    color:white;
    border-color: black;
    border:1px solid white;
    padding:3px;
    transition: 0.3s;
    font-size:20px;
  }
  button:hover{
    padding:10px;
  }
  a{
    color:white
  }
</style>
{#each 't' as letter,i}
     {#if visable}
      <button in:fade={{delay: s + i * 50, duration: 800}}><a href="./game.html">Begin</a></button>
     {/if}
{/each}