<script>
  import { onMount } from "svelte";

  let date = new Date();
  $: hour = date.getHours();
  $: min = date.getMinutes();
  $: sec = date.getSeconds();

  onMount(() => {
    const interval = setInterval(() => {
      date = new Date();
    }, 1000);
  });
</script>

<div class="select-none">
  {hour.toLocaleString('sv-SE', {minimumIntegerDigits: 2, useGrouping:false})} : 
  {min.toLocaleString('sv-SE', {minimumIntegerDigits: 2, useGrouping:false})} : 
  {sec.toLocaleString('sv-SE', {minimumIntegerDigits: 2, useGrouping:false})}
</div>
