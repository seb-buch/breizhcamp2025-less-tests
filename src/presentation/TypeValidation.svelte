<script>
	import Slide from '$lib/Slide.svelte';
	import MeetingExample from './MeetingExample.svelte';
</script>

<style lang="css">
  ul {
    list-style: none;
    line-height: 2em;
  }
</style>

<section>
	<Slide>
		<h2>Validation des types</h2>
	</Slide>

	<Slide>
		<h3>Deux stratégies combinées</h3>

		<ul>
			<li><strong>Validation structurelle</strong> via le framework</li>
			<li><strong>Validation métier</strong> via des constructeurs intelligents</li>
		</ul>

		<aside class="notes">
			On sépare bien la validation technique (types, formats...) de la validation métier
			(invariants,
			contraintes spécifiques). Cela permet de rendre les erreurs explicites et de garantir que les
			objets métiers sont toujours valides.
		</aside>
	</Slide>

	<MeetingExample />
</section>
