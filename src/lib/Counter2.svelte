<script lang="ts">

    // Read count from session storage
    let count = parseFloat(sessionStorage.getItem('count2')) || 15;
  
    const increment = () => {
      count += 0.5
    }
  
    const decrement = () => {
      count -= 0.5
    }
  
    // Write count to session storage
    $: sessionStorage.setItem('count2', count.toString())
  
  </script>
  
  <div class="flex space-x-2 text-center justify-center mt-2 select-none">
    <button on:click={decrement} class="border-2 border-white rounded-xl p-1 hover:border-slate-400 w-8">-</button>
    
    <h4 class="w-16 border-white border-2 rounded-xl justify-center pt-1 text-center">{count.toFixed(1)}&deg;</h4>
    
    <button on:click={increment} class="border-2 border-white rounded-xl p-1 hover:border-slate-400 w-8">+</button>
  </div>