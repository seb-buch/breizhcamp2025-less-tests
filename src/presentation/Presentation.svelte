<script lang="ts">
	import './assets/styles.css';
	import './assets/additional.css';
	import Title from './Title.svelte';
	import IntroTests from './IntroTests.svelte';
	import TypingAndProgLang from './TypingAndProgLang.svelte';
	import '@catppuccin/highlightjs/css/catppuccin-latte.css';
	import TypingInAction from './TypingInAction.svelte';
	import TypingAndTesting from './TypingAndTesting.svelte';
	import TypeValidation from './TypeValidation.svelte';
	import Conclusion from './Conclusion.svelte';
	import Acknowledgement from './Acknowledgement.svelte';
</script>

<svelte:head>
	<title>
		Le meilleur test, c'est celui qu'on n'a pas à écrire!
			&ndash;
			Sébastien Buchoux
	</title>
</svelte:head>

<Title />
<IntroTests />
<TypingAndProgLang />
<TypingInAction />
<TypingAndTesting />
<TypeValidation />
<Conclusion />
<Acknowledgement />
