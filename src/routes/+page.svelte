<script lang="ts">
	import 'reveal.js/dist/reveal.css';

	import Reveal, { type Options } from 'reveal.js';
	import RevealHighlight from 'reveal.js/plugin/highlight/highlight';
	import RevealNotes from 'reveal.js/plugin/notes/notes';
	import RevealMath from 'reveal.js/plugin/math/math';
	import { onMount, tick } from 'svelte';
	import Presentation from '../presentation/Presentation.svelte';
	import { checkSlideDimensions } from '$lib/core';

	export let reveal: Options = {
		slideNumber: true,
		showSlideNumber: 'all',
		controls: false,
		transition: 'none',
		backgroundTransition: 'none',
		hash: true,
		width: 1920,
		height: 1080,
		plugins: [RevealHighlight, RevealNotes, RevealMath.KaTeX],
		center: true
	};

	onMount(async () => {
		await tick();
		const deck = new Reveal(reveal);
		deck.on('slidechanged', checkSlideDimensions);
		deck.on('ready', checkSlideDimensions);
		await deck.initialize();
		console.log('Presentation is ready!');
	});


</script>

<svelte:head>
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/devicon.min.css">
	<script src="https://kit.fontawesome.com/b8d279694e.js" crossorigin="anonymous"></script>
</svelte:head>

<div class="reveal">
	<div class="slides">
		<Presentation />
	</div>
</div>
