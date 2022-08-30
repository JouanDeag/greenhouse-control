<script lang="ts">
  import Counter from "./lib/Counter.svelte";
  import Counter2 from "./lib/Counter2.svelte";
  import Clock from "./lib/Clock.svelte";
  import Timer from "./lib/Timer.svelte";
  import Timer2 from "./lib/Timer2.svelte";

  import data from "./data.json";

  export let title = "VäxthusTM";
  export let header = "Växthuskontroll";
  export let humidity = data.humidity;
  export let temperature = data.temp;

</script>

<svelte:head>
  <title>{title}</title>
</svelte:head>

<main>
  <h1 class="text-center m-10 text-2xl select-none">{header}<span class="text-xs align-top">&trade;</span></h1>

  <div class="flex flex-row space-x-20 justify-center pb-10">
    <h3>Klockan är: <Clock /></h3>
    <h3 class="text-center">Nattemperatur mellan: <Timer /> och <Timer2 /></h3>
    <h3>Luftfuktighet: <div class="select-none">{humidity}%</div></h3>
    <h3>Nuvarande temperatur: <div class="select-none">{temperature}&deg;</div></h3>
  </div>
  <div class="flex flex-row justify-center space-x-10">
    <div class="card text-center">
      <h4 class="">Dagtemperatur</h4>
      <Counter />
    </div>
    <div class="card text-center">
      <h4 class="">Nattemperatur</h4>
      <Counter2 />
    </div>
  </div>
  <div class="text-center align-bottom pt-10">
    Copyright<span class="align-top text-xs">&copy;</span> Johan Karlsson 2022<span class="align-top text-xs">&trade;</span>
  </div>
</main>
