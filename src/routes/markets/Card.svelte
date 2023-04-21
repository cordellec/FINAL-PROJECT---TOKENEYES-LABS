<script> 

export let data ;

</script>


<div class="flex justify-start m-8 mr-8 gap-4 overflow-x-auto flex-wrap">
  
  <div class="card w-48 variant-ghost hover px-2 py-4 flex flex-col items-center"> 

    


  {#if data.symbol === "BTC"}
  <img src="/images/btc.png" alt="btc-photo" class="w-20 h-50">
  {:else if data.symbol === "ETH"}
  <img src="/images/ethereum1200x1200.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "USDT"}
  <img src="/images/usdt.png" alt="usdt-photo" class="w-20 h-50">
  {:else if data.symbol === "BNB"}
  <img src="/images/bnb.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "USDC"}
  <img src="/images/usdc.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "XRP"}
  <img src="/images/ripple1200x1200.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "ADA"}
  <img src="/images/ada.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "DOGE"}
  <img src="/images/doge.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "MATIC"}
  <img src="/images/polygon1200x1200.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "SOL"}
  <img src="/images/sol.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "DOT"}
  <img src="/images/dot.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "BUSD"}
  <img src="/images/busd.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "LTC"}
  <img src="/images/litecoin.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "SHIB"}
  <img src="/images/shibainu.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "AVAX"}
  <img src="/images/avax.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "TRX"}
  <img src="/images/tron.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "DAI"}
  <img src="/images/dai.png" alt="eth-photo" class="w-20 h-50">
  {:else if data.symbol === "WBTC"}
  <img src="/images/wbtc.png" alt="eth-photo" class="w-20 h-50">
  {:else}
  <p>not photo</p>
  {/if}
<br>
  <p id="hero">Rank: {data.rank}</p>
    <p id="hero"> {data.symbol}</p>
    <p id="hero"> {data.name}</p>
    <p id="hero"> Price {(Math.round(data.priceUsd*1000) / 1000).toFixed(2)}</p>
  

  
</div>
</div>

    


