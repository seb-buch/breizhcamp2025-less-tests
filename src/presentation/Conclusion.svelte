<script>
	import Slide from '$lib/Slide.svelte';
	import VerticalSpacer from '$lib/VerticalSpacer.svelte';
</script>

<style lang="css">
  p {
    line-height: 2em;
  }
</style>
<Slide>
	<h2>À retenir</h2>

	<VerticalSpacer height="1em" />
	<p class="fragment">Utiliser des types de données calqués sur le métier</p>
	<p class="fragment">Valider à la création</p>
	<p class="fragment">Testez votre logique métier, pas vos outils</p>

	<aside class="notes">
		On conclut cette partie sur les bonnes pratiques à adopter quand on interagit avec des données
		externes : ne jamais supposer qu’un objet est valide simplement parce qu’il passe une
		validation
		technique.
	</aside>
</Slide>
