<script>
	import { onMount } from 'svelte';

	export let url;
	export let parentWidth;
	export let sideBarWidth;

	let top;
	let left;
	let h;
	let w = 0;

	onMount(() => {
		top = Math.floor(Math.random() * 100);
		left = Math.floor(Math.random() * (parentWidth - w - sideBarWidth) + sideBarWidth);
	});
</script>

<div
	bind:clientWidth={w}
	bind:clientHeight={h}
	style="position: absolute; top: {top}px; left: {left}px"
>
	<img src={url} alt={url} width="600px" />
</div>

<style>
	div {
		display: inline-block;
		  /*border: ;*/
	    /*border:2px solid #000000;*/
	      /*shadow: */
	    /*box-shadow: 5px 5px 5px #000000;
	    -moz-box-shadow: 5px 5px 5px #000000;
	    -webkit-box-shadow: 5px 10px 5px #000000;
	    -khtml-box-shadow: 5px 5px 5px #000000;*/
	}
</style>
