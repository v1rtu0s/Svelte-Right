<script>

import 'chota';
import {Input,Button,Card,Container,Icon,Row,Col} from 'svelte-chota';
import { tweened } from 'svelte/motion';
	import { cubicOut } from 'svelte/easing';

	const progress = tweened(0, {
		duration: 500,
		easing: cubicOut
	});

  var trys = "";
  var odds = "";
  var result = "";

function rechne() {
  
  var prozent = 1-parseFloat(odds)/100;
  var hoch = parseInt(trys);
  console.log(prozent, hoch);

let vorresult = Math.pow(prozent, hoch)*100;
result = vorresult.toPrecision(5);

console.log(result);
progress.set(parseFloat(result));
return result;



 }
 

</script>

<main>
 
<Card>

  <h1>ODDS-WIZARD</h1>

  <Card>
  <Row>
<Col>
  <Icon src="src\assets\times.svg" width="28px" size="2" spin="5" alt=""></Icon><input class="input" bind:value={trys} type="number" placeholder="Versuche?">

</Col>

<Col>
  <Icon src="src\assets\chance.svg" width="28px" size="2" spin="5" alt=""></Icon><input class="input" bind:value={odds} type="number" placeholder="Chance?">

</Col>

  </Row>

</Card>
  <p></p>
  <p2>Chance, dass</p2>
 <p>{odds}%</p>
  <p2>bei</p2>
  <p>{trys} Rolls</p>
  <p2> nicht kommt:</p2>
  <br>


<Button primary outline on:click="{rechne}">Rechne</Button>
<div class="ergebnis">{$progress}%</div>
  

</Card>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

 
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 80rem;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
    font-weight: bold;
    font-size: large;
    text-align: center;
    align-items: center;
    align-content: center;
    align-self: center;
  }

  p2 {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
    font-size: small;
  }

  .ergebnis {
align-self: center;
line-height: 1.5;
    font-size: big;
    font-weight: 700;
    font-size:large;



  }

.input {
  width: 8rem;
  max-width: 12rem;
  height: 4rem;
    margin: 1rem auto;
    line-height: 1.35;
    font-size: small;


}
  
</style>
