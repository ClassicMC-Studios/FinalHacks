<script>
  export let lang;
  import Modal,{getModal} from './Modal4.svelte'
  let dark  ;
  export let butt;
	let selection
	function setSelection(res){
		selection=res
	}
  import fin from '../jsons/newfinnish.json'
  import hin from '../jsons/hindifin.json'
  import cat from '../jsons/catalanfin.json'
  import tag from '../jsons/tagalogfin.json'
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
<button class:white={dark}  on:click={()=>getModal().open()}>
  {butt}
</button>
<Modal>
  <em>
    <textarea name="" id="" style="background-color:rgba(0,0,0,0); width:500px;height:300px; color:white;" placeholder="Type your notes here"></textarea>
  {#if lang == 0}
  <br/>  I was asleep at night is : {fin.i} {fin.was} {fin.asleep} {fin.at} {fin.night}<br/>
Does your dad like me is : {fin.does} {fin.your} {fin.dad} {fin.like} {fin.me}<br/>
The family does not believe me is: {fin.the} {fin.family} {fin.does} {fin.not} {fin.believe} {fin.me} <br/>
I stabbed my family: {fin.i} {fin.stabbed} {fin.my} {fin.family}
  {:else if lang == 1}
  <br/>  I was asleep at night is : {cat.i} {cat.was} {cat.asleep} {cat.at} {cat.night}<br/>
Does your dad like me is : {cat.does} {cat.your} {cat.dad} {cat.like} {cat.me}<br/>
I stabbed my family: {cat.i} {cat.stabbed} {cat.my} {cat.family}<br/>
The family does not believe me is: {cat.the} {cat.family} {cat.does} {cat.not} {cat.believe} {cat.me} 
  {:else if lang  == 2}
  <br/>  I was asleep at night is : {hin.i} {hin.was} {hin.asleep} {hin.at} {hin.night}<br/>
Does your dad like me is : {hin.does} {hin.your} {hin.dad} {hin.like} {hin.me}<br/>
The family does not believe me is: {hin.the} {hin.family} {hin.does} {hin.not} {hin.believe} {hin.me} <br/>
I stabbed my family: {hin.i} {hin.stabbed} {hin.my} {hin.family}
{:else if lang == 3}
  <br/>  I was asleep at night is : {tag.i} {tag.was} {tag.asleep} {tag.at} {tag.night}<br/>
Does your dad like me is : {tag.does} {tag.your} {tag.dad} {tag.like} {tag.me}<br/>
The family does not believe me is: {tag.the} {tag.family} {tag.does} {tag.not} {tag.believe} {tag.me} <br/>
I stabbed my family: {tag.i} {tag.stabbed} {tag.my} {fin.family}
{/if}
  </em>
</Modal>
