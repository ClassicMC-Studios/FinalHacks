<script>
    export let lang;
  import Modal,{getModal} from './Modal.svelte'
  let dark  ;
  export let butt;
	let selection
	function setSelection(res){
		selection=res
	}
  let phrase = "Why That was the last word I heard from him He was asleep not expecting an eventful night but he knew what he did to me I broke into their house and first stabbed the dog I took them out one by one and then woke up the dad And that was the last thing anyone in that family said I knew they would have come for me There was no thought in my mind against that The police would not believe me I had to disappear"
  phrase = phrase.split(" ")
  import fin from '../jsons/newfinnish.json'
  import hin from '../jsons/hindifin.json'
  import cat from '../jsons/catalanfin.json'
  import tag from '../jsons/tagalogfin.json'
</script>
<link rel="stylesheet" href="https://pyscript.net/releases/2024.5.2/core.css">
<svelte:head>
<script type="module" src="https://pyscript.net/releases/2024.5.2/core.js"></script>
<script src="http://code.jquery.com/jquery-3.3.1.min.js" integrity="sha256-FgpCb/KJQlLNfOu91ta32o/NMZxltwRo8QtmkMRdAu8=" crossorigin="anonymous"></script>
</svelte:head>
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
        <!-- <py-script>
import random
from pyscript import display
# USER COSTOMIZE SETTINGS
clusters = False
endCons = False
# Set letter glyphs
con = ['l','p','s','t','k','n','v']
vow = ['a','u','i']
clus = []
diph = []
length = [2,10]
# END CUSTOMIZATION

# Pure random letter generator FIXED tells it which letter group 
def genLetter(fixed):
    if fixed == 0:
        return [con[random.randrange(1,len(con))],'C']
    if fixed == 1:
        return [vow[random.randrange(1,len(vow))],'V']
    if fixed == 2:
        return [clus[random.randrange(1,len(clus))],'CC']
    if fixed == 3:
        return [diph[random.randrange(1,len(diph))],'VV']
# The word generator itself cvc is an array with 
def genWord():
    word = []
    cvc = []
    wordLen = random.randrange(length[0],length[1])
    # Clusters asks if it should include for example ST or SL
    if clusters == False:
        for i in range(wordLen):
            if i == 0:
                tempLet = genLetter(random.randrange(0,2))
                word.append(tempLet[0])
                cvc.append(tempLet[1])
            else:
                if cvc[i-1] == "C":
                    tempLet = genLetter(1)
                    word.append(tempLet[0])
                    cvc.append(tempLet[1])
                else:
                    tempLet = genLetter(0)
                    word.append(tempLet[0])
                    cvc.append(tempLet[1])
    else:
        for i in range(wordLen):
            if i == 0:
                tempLet = genLetter(random.randrange(0,3))
                word.append(tempLet[0])
                cvc.append(tempLet[1])
            else:
                if cvc[i-1] == "C" or cvc[i-1] == "CC":
                    fix = random.randrange(1,3)
                    if fix == 2:
                        fix+=1
                    tempLet = genLetter(fix)
                    word.append(tempLet[0])
                    cvc.append(tempLet[1])
                else:
                    fix = random.randrange(0,2)
                    if fix == 1:
                        fix+=1
                    tempLet = genLetter(fix)
                    word.append(tempLet[0])
                    cvc.append(tempLet[1])
    if cvc[len(cvc)-1] == "C" and endCons == False:
        word.append(genLetter(1)[0])
    print("### Weston's Conlanger ###")
    return ("".join(word)).capitalize()
    print("Structure:"+"".join(cvc))
other = []
phrase = "why that was the last word I heard from him he asleep not expecting an eventful night but knew what did to me broke into their house and first stabbed dog took them out one by then woke up dad thing anyone in family said they would have come for there no thought my mind against police wouldn't believe had disappear"
broke = phrase.split(" ")
final = "Why That was the last word I heard from him He was asleep not expecting an eventful night but he knew what he did to meI broke into their house and first stabbed the dog I took them out one by one and then woke up the dad And that was the last thing anyone in that family said I knew they would have come for meThere was no thought in my mind against that The police wouldn't believe me I had to disappear"
finalbroke = final.split(" ")
for i in range(len(broke)):
    other.append(genWord())
for i in range(len(finalbroke)):
    if any(finalbroke[i] in i for i in broke):
        display("skibisi")
    </py-script>  -->
    <!-- Why? That was the last word I heard from him. He was asleep not expecting an eventful night, but he knew what he did to me.I broke into their house and first stabbed the dog. I took them out one by one, and then woke up the dad. And that was the last thing anyone in that family said. I knew they would have come for me. There was no thought in my mind against that. The police wouldn't believe me, I had to disappear.    -->
    {#each phrase as p,i}
      <span>
        {#if lang == 0}
        {fin[p.toLocaleLowerCase()]}{:else if lang == 1}
        {cat[p.toLocaleLowerCase()]}{:else if lang == 2}
        {hin[p.toLocaleLowerCase()]}{:else if lang == 3}
        {tag[p.toLocaleLowerCase()]}
        {/if}
      </span>  {#if i == 10 ||i == 20 ||i == 30||i == 40||i == 50||i == 60||i == 70||i == 75}<br/>{/if}
    {/each}
    
  </em>
</Modal>
