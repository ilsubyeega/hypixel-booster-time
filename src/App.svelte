<script>
	import { onMount } from 'svelte';
	import Timer from './Timer.svelte';
	let loaded = false;
</script>



<main>
	<Timer title="Blitz Survival Gamez" offsetmin=26 offsetsec=37></Timer>
	<Timer title="Tnt Games" offsetmin=12 offsetsec=07></Timer>
	<Timer title="Mega Walls" offsetmin=28 offsetsec=43></Timer>
	<Timer title="Arcade" offsetmin=11 offsetsec=57></Timer>
	<Timer title="UHC Champions" offsetmin=57 offsetsec=11></Timer>
	<Timer title="Cops and Crims" offsetmin=28 offsetsec=56></Timer>
	<Timer title="Warlords" offsetmin=13 offsetsec=33></Timer>
	<Timer title="Smash Heroes" offsetmin=33 offsetsec=47></Timer>
	<Timer title="Skywars" offsetmin=23 offsetsec=14></Timer>
	<Timer title="Classic Games" offsetmin=15 offsetsec=12></Timer>
</main>
