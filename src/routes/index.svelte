<script context="module">
  export const load = async ({fetch}) => {
    // const res = await fetch('https://jsonplaceholder.typicode.com/posts');
    const res = await fetch('https://api.sheety.co/76ad47b2d5b6382b8a64c0ad92494661/legoProject/legos');
    const data = await res.json();
    const legos = data.legos;
    if(res.ok){
      return {
        props: {
          legos
        }
      }
    } else {
      throw new Error('Could not get lego info')
    }
  }
</script>

<script> 
  import LegoCard from '$lib/components/LegoCard.svelte';

  export let legos;
  let legosCity = [];
  let legosMario = [];
  let legosDisney = [];
  let legosStarWars = [];
  let legosDinosaur = [];
  let legosMinecraft = [];
  let legos3in1 = [];

  legos.forEach(lego => {
    switch (lego.category) {
      case 'City':
        legosCity.push(lego)
        break;
      case 'Disney':
        legosDisney.push(lego);
        break;
      case 'Super Mario':
        legosMario.push(lego);
        break;
      case 'Star Wars':
        legosStarWars.push(lego);
        break;
      case 'Dinosaur':
        legosDinosaur.push(lego);
        break;
        case 'Minecraft':
        legosMinecraft.push(lego);
        break;
        case '3-1 Creator':
        legos3in1.push(lego);
        break;
      default:
        break;
    }
  });


</script>


<div class="container">

  <div class="grid-container">
    <h2 class="grid-title">City Legos</h2>
    {#each legosCity as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>

  <div class="grid-container">
    <h2 class="grid-title">Super Mario Legos</h2>
    {#each legosMario as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>

  <div class="grid-container">
    <h2 class="grid-title">Disney Legos</h2>
    {#each legosDisney as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>

  <div class="grid-container">
    <h2 class="grid-title">Star Wars Legos</h2>
    {#each legosStarWars as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>

  <div class="grid-container">
    <h2 class="grid-title">Dinosaur Legos</h2>
    {#each legosDinosaur as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>

  <div class="grid-container">
    <h2 class="grid-title">3-1 Legos</h2>
    {#each legos3in1 as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>

  <div class="grid-container">
    <h2 class="grid-title">Minecraft Legos</h2>
    {#each legosMinecraft as lego }
        <LegoCard {lego}/>   
    {/each}
  </div>


</div>



<style>

  .grid-container {
    padding: 1rem;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 1.2rem;
  }

  .grid-title{
    grid-column: 1/-1;
  }

</style>

