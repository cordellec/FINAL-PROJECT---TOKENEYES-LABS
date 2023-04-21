<script>
  import getCryptoData from "./api";
	import { onMount } from "svelte";

import Card from "./Card.svelte";

let cryptoData = [];

onMount(async () => {
  const res = await getCryptoData ();
  console.log(res)
  cryptoData = res.data


})
</script>


<center>
  
  <div class="flex justify-start m-8 gap-4 overflow-x-auto flex-wrap"> 
  {#each cryptoData as crypto}

  <Card data={crypto} /> 

  {/each}

</div>

</center>


