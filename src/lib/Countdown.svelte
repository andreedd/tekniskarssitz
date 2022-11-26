<script>
	import { onMount, afterUpdate, onDestroy } from "svelte";

	// default prop is 10
    let countDownDate = new Date("Feb 4, 2023 00:00:00").getTime();

    let countdownText = calculateTime()[0];
    $: now = calculateTime()[1];
	let timer = null;

	// when countdown update, update displayValue
	$: displayValue = countdownText;

	onMount(() => {
	  timer = setInterval(() => {
        countdownText = calculateTime()[0];
	  }, 1000);
	});

	afterUpdate(() => {
	  if (new Date().getTime() > countDownDate) {
	    if (timer) {
	      clearInterval(timer);
	      timer = null;
	    }
	  }
	});

	onDestroy(() => {
	  if (timer) {
	    clearInterval(timer);
	  }
	});

    function calculateTime(){
        now = new Date().getTime();
        let distance = countDownDate - now;

        // Time calculations for days, hours, minutes and seconds
        let days = Math.floor(distance / (1000 * 60 * 60 * 24));
        let hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        let minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        let seconds = Math.floor((distance % (1000 * 60)) / 1000);

        let timeString = days + "d " + hours + "h " + minutes + "m " + seconds + "s ";;

        return [timeString, now]
    }
</script>

{#if now > countDownDate }
<h1>🎊</h1>
{:else}
<h1>{displayValue}</h1>
{/if}