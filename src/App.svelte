<script>
	// import { fade } from 'svelte/transition';
	import HernanFoto from './HernanFoto.svelte';

	const leftMin = 50;
	const topMin = 0;

	let h;
	let w;


	let textJahrder = "olympus mju-II";
	let textCopycat = "<h3>Copycat</h3><p>a bunch of scans made with a handhold scanner.</p>";


	let albumJahrder = [
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
	

	let albumCopycat = [
		'https://64.media.tumblr.com/5c6833b97ee0b06e9a0732d36e3a60dc/tumblr_n1965vobGl1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/f33c7409c77b67feffe8542ce339374d/tumblr_n1964iZ1Ay1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/b036090d74b1d2a92bd928149b69caec/tumblr_n1963lSNKE1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/e8eb12258f4271b31b1c8ccf39140703/tumblr_n19631a5fe1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/5d426c61e22e18c60c5973568c5a160f/tumblr_n1962pDCuR1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/ad251692a0d76bf6126fed1c3babb4fb/tumblr_n195z9xL5c1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/afb0eecf4d7d65ec3328e8cd328c4fd2/tumblr_n195y0bpkS1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/ac6e0ff94f1ecd5967f0b0e4914aaeb1/tumblr_n195xaPZR21t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/2bb92311c731a2c8627c98402b2fc8d0/tumblr_n195v1VCCp1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/914d1d5eba8cabec55df81ec238c6e85/tumblr_n1950exbyn1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/fe7d14d344c7d195d51d570f33f41bd3/tumblr_n194xyvCCW1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/eb3fc33f391f108a9e20de3a30169c69/tumblr_n07ed7PBoR1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/7669e20dea6bef2a97a8f23adfd066ac/tumblr_n07e6fIbwK1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/f7d2f28a8788f8f7e4e4ab9f28c16ecf/tumblr_myya9s07kX1t8vj3ro1_1280.jpg',
		'https://64.media.tumblr.com/7a98f79cd9fa5eb70cb2d992a2495c3c/tumblr_mxy1no5wtj1t8vj3ro1_1280.jpg'
		];
	


	let current = 'jahr';
	let images = albumJahrder;
	let infoText = textJahrder;
	let displayStack = [];
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
		if ( fotoIndex > images.length ) {
			// fotoIndex = images.length
			fotoIndex = 0;
		} else {
			displayStack = [...displayStack, img];
		};
	};
	const handleRemove = () => {
		displayStack = displayStack.slice(0, -1);
		fotoIndex--;
		if ( fotoIndex < 0 ) {
			fotoIndex = 0
		};
	};

	const changetoJahrder = () => {
		current = 'jahr';
		images = albumJahrder;
		infoText = textJahrder;
		fotoIndex = 0
	};
	const changetoCopycat = () => {
		current = 'copy';
		images = albumCopycat;
		infoText = textCopycat;
		fotoIndex = 0
	};
	const clearStack = () => {
		displayStack = [];
		// fotoIndex = 0
	};

	// $: {
	// 	console.log(w);
	// 	console.log(h);
	// }
</script>

<div class="wrapper" bind:clientWidth={w} bind:clientHeight={h}>
	<button class="btn btnPlus" on:click={handleAdd}> + </button>
	<button class="btn btnMinus" on:click={handleRemove}> - </button>
	<button class="btn btnJahrder" class:selected="{current === 'jahr'}" on:click={changetoJahrder}> Jahr der </button>
	<button class="btn btnCopycat" class:selected="{current === 'copy'}" on:click={changetoCopycat}> Copycat </button>
	<button class="btn btnClear" on:click={clearStack}> clear </button>

	{#each displayStack as image}
		<HernanFoto url={image.url} parentWidth={w} sideBarWidth={0} />
	{/each}
</div>

<section class='info'>
	{@html infoText}
</section>

<style>
	.wrapper {
		min-height: 100%;
	}

	button {
		position: fixed;
		z-index: 999;
		width: 100px;
	}

	.body{
		background-color: green;
	}
  	.btnPlus, .btnMinus, .btnJahrder, .btnCopycat, .btnClear{
  		color: blue;
  		background: white;
  		border: none;
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
  		left:  50px;

  	}

 	.btn:hover {
   /*background: #e1e1e1;*/
   		border: 2px solid #000000;
	}


	.selected {
		background-color: #9e8bff;
		/*color: white;*/
	}


	 .btnPlus{
	 	top:  50px;
  		font-size: xx-large;
    } 
	.btnMinus {
		top: 100px;
  		font-size: xx-large;
	}
	.btnClear {
		top: 150px;
		font-size: x-large;
	}
	.btnJahrder {
		top: 250px;
		font-style: oblique;
	}
	.btnCopycat {
		top: 300px;
		font-style: oblique;
	}
	.info {
		padding: 10px;
		position: fixed;
		z-index: 999;
		width: 200px;
  		color: blue;
  		background: white;
  		border: none;
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
  		right:  50px;

	 	top:  50px;
	}
</style>
