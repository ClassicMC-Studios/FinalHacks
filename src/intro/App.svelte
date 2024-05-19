<script>
  import { fade } from 'svelte/transition';
  import Txt from './lib/txt.svelte'
  import Roll from './lib/roll.svelte'
  import Renderon from './lib/renderon.svelte'
  import Renderbutt from './lib/renderbutt.svelte';
  let visable = false;
  let y;
  function startUp(){visable = true;} 
</script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>
  :global(body){
    background-image: url(./lib/scock3.jpg);
    background-repeat: none;
    background-size:cover;
    background-color:#fff;
    background-attachment: fixed;
    color:white;
  }
</style>
<svelte:window bind:scrollY={y} on:load={startUp()}/>
<main>
  {#each 'Confession' as letter, i}
    {#if visable}
      <span class="h1" in:fade={{delay: 100 + i * 150, duration: 800}}>{letter}</span>
    {/if}
  {/each}<br/>
  <Txt txt='In axit orem des livi'/><br/><br/><br/><br/>
  
  {#if visable}
    <div in:fade={{delay: 2510 + 2 * 150, duration: 800}}>    
      <Roll/>
    </div>
  {/if}
</main>
<maintwoelectricbogaloo>
  <Renderon s={100} visable={y>120} txt="Hello, Detective..."/>
    <br/><br/>
  <Renderon s={1000} visable={y>120} txt="You got selected to check on a possible crime at [----------]."/><br/><br/>
  <Renderon s={4000} visable={y>120} txt="I hope you are up to the task."/> &nbsp;&nbsp;&nbsp;&nbsp; 
    <Renderbutt s={5000} visable={y>120}/>
    <p style="opacity:0;">sus</p>
</maintwoelectricbogaloo>
