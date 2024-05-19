<script>
  export let lang;
  import Modal,{getModal} from './Modal2.svelte'
  let dark  ;
  export let butt;
	let selection
	function setSelection(res){
		selection=res
	}
  let name = ""
  import fin from '../jsons/newfinnish.json'
  import hin from '../jsons/hindifin.json'
  import cat from '../jsons/catalanfin.json'
  import tag from '../jsons/tagalogfin.json'
  let translateT = 0
  let allow;
  function send(){
    if(translateT <=19){
      allow = name
      translateT ++;
    }
  }
</script>
<!-- <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"> -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
<style>.white{color:rgb(255, 255, 255)!important;}.bleu{color:rgb(108, 108, 239);}button{
  background-color: hsla(0, 0%, 27%, 0);
  border-radius: 0;
  color:white;
  border-color: black;
  border:1px solid white;
  padding:10px;
  /* transition: 0.3s; */
  font-size:20px;
  margin:10px;
}
input{
  background-color: rgba(0,0,0,0);
  border: 1px solid white;
  padding:5px;
  color:white;
}
button:hover{
  /* padding:20px; */
}</style>
<button class:white={dark}  on:click={()=>getModal().open()}>
  {butt}
</button>
<Modal>
  <!-- <em>
    <input type="text" placeholder="Speak here"> <button><i class="fa fa-send"></i></button>
  </em><br/> -->
  <em>
    <input type="text" bind:value={name} placeholder="Translator"> <button on:click={send}><i class="fa fa-language"></i></button>
    <br/>
    {#if allow != undefined}
    {allow} : {#if lang==0}{fin[allow.toLocaleLowerCase()]}{:else if lang==1}{cat[allow.toLocaleLowerCase()]}{:else if lang == 2}{hin[allow.toLocaleLowerCase()]}{:else if lang == 3}{tag[allow.toLocaleLowerCase()]}{/if}
    {/if}
  </em><br/>
  <b style="font-style:italic;">Only {20-translateT} left</b>
</Modal>
