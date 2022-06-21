<script>
  var trys = "";
  var odds = "";
  var result = "";

function rechne() {
  
  var prozent = 1-parseFloat(odds)/100;
  var hoch = parseInt(trys);
  console.log(prozent, hoch);

let vorresult = Math.pow(prozent, hoch)*100;
result = vorresult.toFixed(10);

console.log(result);
return result;



 }
 

</script>

<main>
 
  <h1>ODDS-WIZARD</h1>

  <input bind:value={trys} type="number" placeholder="Versuche?">
  <input bind:value={odds} type="number" placeholder="Chance?">
  <p></p>
  <p2>Chance, dass</p2>
 <p>{odds}%</p>
  <p2>bei</p2>
  <p>{trys} Rolls</p>
  <p2> nicht kommt:</p2>


<button on:click="{rechne}">Rechne</button>
<p>{result}%<p>
  


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
  }

  p2 {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
    font-size: small;
  }


  
</style>
