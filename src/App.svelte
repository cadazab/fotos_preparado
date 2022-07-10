<script>
	// import { fade } from 'svelte/transition';
	import HernanFoto from './HernanFoto.svelte';

	const leftMin = 50;
	const topMin = 0;

	let h;
	let w;

	let images = [
		'https://64.media.tumblr.com/8414b04021aaa283ab403d18fa3dbf00/tumblr_onsv741Nf41v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/2f5c27efedf0f4cbbcc5263e6a5c0790/tumblr_onsus09NZA1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/73303a1e1b2741b529bdb48a74e365f7/tumblr_olqcmbxoSI1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/915620edc746af3b066a23ff1c41418b/tumblr_of9nndxHVq1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/66fd0bdcdb9f60f1555c8fe2b32ce037/tumblr_olqbx9l1KH1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/00478a7763b9787e1b3fe347f729111c/tumblr_olqbt45Pa01v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/1366546fa509edf636888e9c681ee716/tumblr_olqbvuD1Ab1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/3f3f2bba4daf914ac907d51d48a3e3d3/tumblr_obg2tcyNsT1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/98be82efd2bd3855007ba1744edffa5a/tumblr_o915b0FkfJ1v4tpzoo1_1280.jpg'
	];

	let staple = [];

	let fotoIndex = 0;

	const handleAdd = () => {
		const img = {
			style: {
				top: Math.floor(Math.random() * 100) + topMin,
				left: Math.floor(Math.random() * 100) + leftMin
			},
			url: images[fotoIndex]
		};

		fotoIndex++;

		staple = [...staple, img];
	};
	const handleRemove = () => {
		staple = staple.slice(0, -1);
		fotoIndex--;
	};

	$: {
		console.log(w);
		console.log(h);
	}
</script>

<div class="wrapper" bind:clientWidth={w} bind:clientHeight={h}>
	<button class="btnPlus" on:click={handleAdd}> + </button>
	<button class="btnMinus" on:click={handleRemove}> - </button>

	{#each staple as image}
		<HernanFoto url={image.url} parentWidth={w} sideBarWidth={0} />
	{/each}
</div>

<style>
	.wrapper {
		min-height: 100%;
	}

	button {
		position: fixed;
		z-index: 999;
		width: 100px;
	}

	/* .btnPlus{

  } */

	.btnMinus {
		top: 50px;
	}
</style>
