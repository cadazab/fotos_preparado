<script>
	import Foto from './Foto.svelte';
	import {albumCopycat} from './lib/albumCopycat.js'
	import {albumBsas} from './lib/albumBsas.js'
	import {albumJahrder} from './lib/albumJahrder.js'
	import {album2022} from './lib/album2022.js'
	import {albumIndo} from './lib/albumIndo.js'

	const leftMin = 50;
	const topMin = 0;

	// page body dimensions
	let h;
	let w;

	let selectedAlbum = album2022

	// the displayed foto stack
	let displayStack = [];
	let fotoIndex = 0;

	const handleAdd = () => {
		const img = {
			style: {
				top: Math.floor(Math.random() * 100) + topMin,
				left: Math.floor(Math.random() * 100) + leftMin
			},
			url: selectedAlbum.images[fotoIndex]
		};

		fotoIndex++;
		if ( fotoIndex > selectedAlbum.images.length ) {
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
	// album = {name, images, text}
	const changeAlbum = (album) => {
		selectedAlbum = album
		fotoIndex = 0
	}
	const clearStack = () => {
		displayStack = [];
		// fotoIndex = 0
	};
</script>

<div class="wrapper" bind:clientWidth={w} bind:clientHeight={h}>
	<!-- Navigation buttons -->
	<button style="top: 50px;  font-size: xx-large;" class="btn " on:click={handleAdd}> + </button>
	<button style="top: 100px; font-size: xx-large;" class="btn " on:click={handleRemove}> - </button>
	<button style="top: 150px; font-size: x-large;"  class="btn " on:click={clearStack}> clear </button>
	<!-- Album buttons -->
	<button style="top: 250px;" class="btn btnAlbum" class:selected="{selectedAlbum.name === albumJahrder.name}" on:click={()=>changeAlbum(albumJahrder)}> Jahr der </button>
	<button style="top: 300px;" class="btn btnAlbum" class:selected="{selectedAlbum.name === albumCopycat.name}" on:click={()=>changeAlbum(albumCopycat)}> Copycat </button>
	<button style="top: 350px;" class="btn btnAlbum" class:selected="{selectedAlbum.name === albumIndo.name}" on:click={()=>changeAlbum(albumIndo)}> Indochina </button>
	<button style="top: 400px;" class="btn btnAlbum" class:selected="{selectedAlbum.name === albumBsas.name}" on:click={()=>changeAlbum(albumBsas)}> Baires </button>
	<button style="top: 450px;" class="btn btnAlbum" class:selected="{selectedAlbum.name === album2022.name}" on:click={()=>changeAlbum(album2022)}> 2022 </button>
	<!-- Image stack -->
	{#each displayStack as image}
		<Foto url={image.url} parentWidth={w} sideBarWidth={0} />
	{/each}
</div>

<section class='info'>
	{@html selectedAlbum.text}
</section>
<section class='credits'>
	<p>website by cami and me. code on <a href='https://github.com/cadazab/fotos_preparado' color=white>github</a></p>
</section>

<style>
	body {
		background-color: red;
	}
	.wrapper {
		min-height: 100%;
	}
	button {
		position: fixed;
		z-index: 999;
		width: 100px;
	}
	.btn {
   		border: 2px solid #000000;
   		
  		color: blue;
  		background: white;
  		/*border: none;*/
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
  		left:  50px;

  	}
 	.btn:hover {
   		border: 2px solid #FF0000;
	}
	.selected {
		background-color: #9e8bff;
		/*color: white;*/
	}
	.btnAlbum {
		font-style: oblique;
	}
	.info {
		/*position*/
  		right:  50px;
	 	top:  50px;
		position: fixed;
		z-index: 999;
	 	/*box*/
   		border: 2px solid #000000;
		padding: 10px;
		width: 200px;
  		background: white;
  		/*font*/
  		color: blue;
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
	}
	.credits {
		/*box*/
		padding: 10px;
		width: 200px;
		/*position*/
	 	bottom:  50px;
		position: fixed;
		z-index: 999;
  		/*font*/
  		color: white;
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
  		right:  50px;
	}
</style>
