<script>
    import { onMount, onDestroy } from 'svelte';
    export let title;
    export let offsetmin = 0;
    export let offsetsec = 0;
    let currenttime = new Date();
    let arr = [new Date(), new Date(), new Date(), new Date(), new Date(), new Date(), new Date()];
    let nextbooster = new Date();
    let nextboosterstring;
    arr.forEach(function(item, index, array) {
        if (index!=0){
            item.setDate(array[0].getDate()+index-1);
            item.setHours(5, offsetmin, offsetsec, 0);
        }
    })
    nextbooster.setHours(arr[0].getHours(), offsetmin, offsetsec, arr[0].getMilliseconds());

    function getValue(time){
        var a = Math.abs(arr[0] - time) / 1000 / 60;
        var time = a / 60;
        var min = a % 60;
        var sec = a * 60 % 60;
        return `${Math.floor(time)}시간 ${Math.floor(min)}분 ${Math.floor(sec)}초`
    }

    let t;
    function timefunction(){
        arr[0] = new Date();
        nextboosterstring = getValue(nextbooster);
        if (nextbooster < arr[0])
            nextbooster.setHours(arr[0].getHours()+1, offsetmin, offsetsec, arr[0].getMilliseconds());
    }
    onMount(() => {
        t = setInterval(timefunction,500);
    })
    onDestroy(() => {
		clearInterval(t);
	});
</script>
<h>{title} (다음 부스터 활성화: {nextboosterstring})</h>
<br>
{#each arr as item, i}
    {#if (i == 1 && arr[0] < arr[1]) || i > 1}
        {getValue(item)} {item} <br>
    {/if}
{/each}

<style>
h { 
    font-size: 20px;
}
</style>