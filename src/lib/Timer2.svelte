<script>
    let hour = parseFloat(sessionStorage.getItem('hour2')) || 7;
    let min = parseFloat(sessionStorage.getItem('min2')) || 0;


    function add() {
        min += 15;
        if (min === 60) {
            hour += 1;
            min = 0;
        }
    }

    function subtract() {
        if (min == 0) {
            hour -= 1;
            min = 45;
        } else {
            min -= 15;
        }
    }

    $: sessionStorage.setItem('min2', min.toString())
    $: sessionStorage.setItem('hour2', hour.toString())


</script>

<div class="select-none text-center">
    <button class="border-white border-2 rounded-md w-6 hover:border-slate-400" on:click="{add}">+</button>
    {hour.toLocaleString('sv-SE', {minimumIntegerDigits: 2, useGrouping:false})}:{min.toLocaleString('sv-SE', {minimumIntegerDigits: 2, useGrouping:false})}:00
    <button class="border-white border-2 rounded-md w-6 hover:border-slate-400" on:click="{subtract}">-</button>
</div>