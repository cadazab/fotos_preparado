<script>
	// import { fade } from 'svelte/transition';
	import HernanFoto from './HernanFoto.svelte';

	const leftMin = 50;
	const topMin = 0;

	let h;
	let w;


	let textJahrder = "<h3>Das Jahr der Kompaktkamera</h3>Always in the pocket: Olympus &micro;-II";
	let textCopycat = "<h3>Copycat</h3><p>a bunch of scans made with a handhold scanner.</p>";
	let textIndo = "<h3>Indochina</h3><p>2017</p>"


	let albumJahrder = [
		// 'https://64.media.tumblr.com/8414b04021aaa283ab403d18fa3dbf00/tumblr_onsv741Nf41v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/2f5c27efedf0f4cbbcc5263e6a5c0790/tumblr_onsus09NZA1v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/73303a1e1b2741b529bdb48a74e365f7/tumblr_olqcmbxoSI1v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/915620edc746af3b066a23ff1c41418b/tumblr_of9nndxHVq1v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/66fd0bdcdb9f60f1555c8fe2b32ce037/tumblr_olqbx9l1KH1v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/00478a7763b9787e1b3fe347f729111c/tumblr_olqbt45Pa01v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/1366546fa509edf636888e9c681ee716/tumblr_olqbvuD1Ab1v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/3f3f2bba4daf914ac907d51d48a3e3d3/tumblr_obg2tcyNsT1v4tpzoo1_1280.jpg',
		// 'https://64.media.tumblr.com/98be82efd2bd3855007ba1744edffa5a/tumblr_o915b0FkfJ1v4tpzoo1_1280.jpg'
		'https://64.media.tumblr.com/9f3b97768114bf9d12330a2fe61c9cdd/tumblr_o1tsf7pXE71v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/e8cb62ecd6fce82807f1fb37be0e5a52/tumblr_o1tsg0dsMT1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/347d3a01ca00b584b44ce3a54f18094f/tumblr_o1tv8euALw1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/ad83b8f4c856a58c3a93e0198c288e45/tumblr_o1tvbuhz7u1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/1306163d730ac6be81a029486bb7781a/tumblr_o1tvj6Twlv1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/342701f98af4517be78fda175cf68713/tumblr_o1tvlu5MUs1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/8eb5139363445b68789f72f5483e77de/tumblr_o1tvnlGzIN1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/b24b5fe1eeed58442efcf3a89c7dcb26/tumblr_o1tvuecz381v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/d9bee76f751337630ed5d7bacac13892/tumblr_o1xyrtdzyb1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/a37021a217fe2ce35203202f6f124a1e/tumblr_o1xyszNkIX1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/c4a72ce199fd965b5e4052580245903a/tumblr_o1xz1amqEd1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/c4949a727600bb702daf1ebf58dcde95/tumblr_o1xzrvus5N1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/892cb8cc56afc0f48939d1fafd35f98f/tumblr_o1xzyibnSl1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/d5600ea1184a47da733ad98e1efaf094/tumblr_o1y020GIIV1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/eb1eb773e3b1362c289d7fa614135400/tumblr_o5xis7JXJ41v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/80960ac04ad660601913de0692b798b8/tumblr_o5xjnyxgas1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/5deccc969b6b221f004828d13b3477f2/tumblr_o61f332czO1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/d0bbd7afb9e6bca9e397f16f709e9b18/tumblr_o61f7bojFF1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/1ecb411df0bc7c1a0218c9a47b53bbe0/tumblr_o7lbduHZRv1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/2ffb5e7d2b22ed1d89fe7ee171000206/tumblr_o7lbf8Qn3W1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/2e930217079d3eb3715ae8fa9c121072/tumblr_o7lbhl6pEO1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/13aee145de2187044ab4572e2af69517/tumblr_o7lbmgxMhE1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/fcd473e0e478a6d365ac554014777810/tumblr_o87595kiuU1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/4e03211fe6ed687f2869a71e823c8fc2/tumblr_o875gutgyC1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/6fb9c5933cb9a1eabea96b94e306d8fc/tumblr_o875nhoCW51v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/76d483ed5a9ef0cf99a9dd9890162a5e/tumblr_o914z1gdCR1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/118899cff3fb0fded0c33579f4a52e1e/tumblr_o914wtbnPB1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/dbae12f7a1d9cc21a25b28de5d21e281/tumblr_o9yv3olZBd1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/9b352fdbc064ac4bb1ca7992aefa473c/tumblr_oa4euptl6S1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/d28e8bb70bbb2a8e381a7526487e5d20/tumblr_oa4evb53Sk1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/ee97d3cc21c02a8e2ca6b9f98a989d5c/tumblr_oablxpGsQx1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/2d1141ba2a900a21d9faa4d7573d1058/tumblr_oablz8Opcs1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/d574c0b1a230c7833e443dfdc3397cb5/tumblr_oabm059hru1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/8a2d7e5cba90bf0320ee7bd4a6cd65f4/tumblr_oanjvu1t7X1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/584b14579fe35812ae77f51331f9c2a0/tumblr_oaxjd2m6jK1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/195928644b6ccdb61aff3d469adf43d1/tumblr_obg2xqxqvV1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/2668d7f1e4b594ef73e18ea678c1fc22/tumblr_obg31pMife1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/fae5d76256132720574abd0b87369bb2/tumblr_obg35pIzeo1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/aeb80864b159f3bb6df43918d2ffc7ec/tumblr_obg3l6vRmS1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/8f1327bf6dcb65d60fcf31c2ded90bda/tumblr_obg3omQcid1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/5b7bfa45af62b058251dcaedfd0ace74/tumblr_of9np0a8NO1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/a9806a23481b01991bd488d086fd2247/tumblr_of9nqkRtJt1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/1ed2c1e9014a1d7800c57c1f94f6a28c/tumblr_ofm7nkkcym1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/8f01a64adc003321dbd43de8e7d346d2/tumblr_o1xzfkyUH91v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/8cbf6c9a7cdf6291daaf0565f3bce2e6/tumblr_olqc0yjBN31v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/f480d435cd231e96d74ba98098003f8a/tumblr_olqcfs392C1v4tpzoo1_1280.jpg',
		'https://64.media.tumblr.com/6ec3faa39c15e2477e3438ade84e478c/tumblr_onsvek7fSD1v4tpzoo1_1280.jpg'
	].reverse();
	


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
	
	let albumIndo = [
		'https://64.media.tumblr.com/ed00fc5e7e519eb511e34247f513156b/tumblr_o5levaYUxT1vrad2oo1_1280.jpg',
		'https://64.media.tumblr.com/aa820997b20824d3e4a494d24742ef27/tumblr_o5levaYUxT1vrad2oo2_1280.jpg',
		'https://64.media.tumblr.com/51d12d4df1c8c64bb955510db7753283/tumblr_o5levaYUxT1vrad2oo7_1280.jpg',
		'https://64.media.tumblr.com/d40b3f5009aa309d68a9a1dad8b7e238/tumblr_o5levaYUxT1vrad2oo10_1280.jpg',
		'https://64.media.tumblr.com/991f6b6b19f6c1d6acd114c5ac0a44af/tumblr_o5lequRa0e1vrad2oo2_1280.jpg',
		'https://64.media.tumblr.com/0429f64f52d8dbb95cffa7255d735d8b/tumblr_o5lequRa0e1vrad2oo5_1280.jpg',
		'https://64.media.tumblr.com/d5bc1dc30185d2f9673e1c397c9ef05a/tumblr_o5lequRa0e1vrad2oo7_1280.jpg',
		'https://64.media.tumblr.com/d6673d310d12a2d463bc0d03fb95ca1b/tumblr_o5lequRa0e1vrad2oo9_1280.jpg',
		'https://64.media.tumblr.com/b8e3a63068c5023459918837b20b1b73/tumblr_o5lenev4bi1vrad2oo6_1280.jpg',
		'https://64.media.tumblr.com/49b89fb377dceeccd206329de8a416bf/tumblr_o5lenev4bi1vrad2oo9_1280.jpg',
		'https://64.media.tumblr.com/0ebdf48630ce73d2ec09f6101ab804f3/tumblr_o5lenev4bi1vrad2oo10_1280.jpg',
		'https://64.media.tumblr.com/5608fcd1521d4b215e1182c06b7c5b8c/tumblr_o5lejsUJBX1vrad2oo1_1280.jpg',
		'https://64.media.tumblr.com/05ca266f4e41bcfff72c215a8998ff3a/tumblr_o5lejsUJBX1vrad2oo10_1280.jpg',
		'https://64.media.tumblr.com/dedfce54492abe0e12ab260055f35125/tumblr_o5lejsUJBX1vrad2oo2_1280.jpg',
		'https://64.media.tumblr.com/40a311932c119ebd19fdd5b9d6fca951/tumblr_o5lejsUJBX1vrad2oo6_1280.jpg',
		'https://64.media.tumblr.com/393bc69c43495d32291bc794adb4b68f/tumblr_o5lejsUJBX1vrad2oo8_1280.jpg',
		'https://64.media.tumblr.com/21a5e9489c8c3f502516a7f1d4bd2524/tumblr_o5lefp4Wu21vrad2oo3_1280.jpg',
		'https://64.media.tumblr.com/1bdbe17e1beb8ef22e87995c5414db06/tumblr_o5le513ngy1vrad2oo7_1280.jpg',
		'https://64.media.tumblr.com/8bb3a33121a6ace071d8dae20a31769e/tumblr_o5ldw5irYL1vrad2oo4_1280.jpg',
		'https://64.media.tumblr.com/e7c9e17cd4a3d1ad9cfcd05309cafb15/tumblr_o5ldw5irYL1vrad2oo10_400.jpg',
		'https://64.media.tumblr.com/827b87b0a4aa197c8452d795884f459a/tumblr_o5ldw5irYL1vrad2oo8_1280.jpg',
		'https://64.media.tumblr.com/94bfafec263861d555c20b864b8b215e/tumblr_o5ldw5irYL1vrad2oo5_1280.jpg'
		]


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
	const changetoIndo = () => {
		current = 'indo';
		images = albumIndo;
		infoText = textIndo;
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
	<button class="btn btnIndo" class:selected="{current === 'indo'}" on:click={changetoIndo}> Indochina </button>
	<button class="btn btnClear" on:click={clearStack}> clear </button>


	{#each displayStack as image}
		<HernanFoto url={image.url} parentWidth={w} sideBarWidth={0} />
	{/each}
</div>

<section class='info'>
	{@html infoText}
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
   /*background: #e1e1e1;*/
   		border: 2px solid #FF0000;
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
	.btnIndo {
		top: 350px;
		font-style: oblique;
	}
	.info {


   		border: 2px solid #000000;


		padding: 10px;
		position: fixed;
		z-index: 999;
		width: 200px;
  		color: blue;
  		background: white;
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
  		right:  50px;

	 	top:  50px;
	}


	.credits {


   		/*border: 2px solid #000000;*/


		padding: 10px;
		position: fixed;
		z-index: 999;
		width: 200px;
  		color: white;
  		/*background: white;*/
  		font-family: monospace;
  		font-style: bold;
  		font-size: large;
  		right:  50px;

	 	bottom:  50px;
	}


</style>
