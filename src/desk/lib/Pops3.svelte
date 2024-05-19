<script>
  import Modal,{getModal} from './Modal3.svelte'
  let dark  ;
  export let butt;
	let selection
	function setSelection(res){
		selection=res
    }
    let a1,a2,a3,a4,a5;
</script>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>.white{color:rgb(255, 255, 255)!important;}.bleu{color:rgb(108, 108, 239);}button{
  background-color: hsla(0, 0%, 27%, 0);
  border-radius: 0;
  color:white;
  border-color: black;
  border:1px solid white;
  padding:10px;
  transition: 0.3s;
  font-size:20px;
  margin:10px;
}
button:hover{
  padding:20px;
}</style>
<link rel="stylesheet" href="https://pyscript.net/releases/2024.5.2/core.css">
<!-- This script tag bootstraps PyScript -->
<svelte:head>
  <script type="module" src="https://pyscript.net/releases/2024.5.2/core.js"></script>
  <script src="http://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
</svelte:head>
<button class:white={dark}  on:click={()=>getModal().open()}>
  {butt}
</button>
<Modal>
    Was he the killer? <input type="checkbox" bind:checked={a1} name="" id=""><br/>
    Was his first victim a mom? <input type="checkbox" bind:checked={a2} name="" id=""><br/>
    Were his victims stabbed? <input type="checkbox" bind:checked={a3} name="" id=""><br/>
    Was he framed? <input type="checkbox" name="" bind:checked={a4} id=""><br/>
    Did he want to disappear? <input type="checkbox" bind:checked={a5} name="" id=""><br/>
    {#if a1 && !a2 && a3 && !a4 && a5}
      <button on:click={()=>getModal('second').open(setSelection)}>Continue</button>
    {/if}
</Modal>
<Modal id="second">
  <h1>
    You cracked the Mystery!<br/>
  </h1>
  <em>Good Job</em><br/>
    The True confession was:<br/>
    <em>Why That was the last word I heard from him He was asleep not expecting an eventful night <br/>but he knew what he did to me I broke into their house and first stabbed the dog I took them out one by one and then woke up the dad<br/> And that was the last thing anyone in that family said I knew they would have come for me <br/>There was no thought in my mind against that The police would not believe me I had to disappear</em>
</Modal>
