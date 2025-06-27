<script>
	import Slide from '$lib/Slide.svelte';
</script>

<style>


  p {
    padding-bottom: 1em;
  }
</style>

<section>

	<Slide>
		<h3>Les tests, un passage obligé</h3>
		<p>Garantir la qualité du code</p>
		<p>Vérifier les cas limites, les erreurs, les oublis</p>
		<p>Accompagner l’évolution du logiciel</p>

	</Slide>


	<Slide>
		<h3>Mais soyons honnêtes&nbsp;&hellip;</h3>
		<p>Écrire des tests, ce n’est pas toujours fun 😅</p>
		<p class="fragment">On est souvent obligé de couvrir des cas liés à des données erronées </p>
		<p class="fragment">Parfois, on écrit des tests... juste pour éviter un bug "improbable"</p>

	</Slide>

	<Slide>
		<h3>Quelques exemples</h3>
		<p class="fragment">Et si <code>quantity</code> est négative&nbsp;?</p>
		<p class="fragment">Et si <code>user.age</code> n’est pas un entier&nbsp;?</p>
		<p class="fragment">
			Hey [dev référent], dans <code>[nom objet]</code> quand-est ce que <code>[nom attribut]</code>
			est défini ?<br />
			Euh&hellip; Normalement, il est défini si <code>[nom autre attribut]</code> est défini.<br />
			Euh&hellip; T'es sûr&nbsp;?<br />
			Euh&hellip; Ben, normalement &hellip;<br />
			Euh&hellip; Ben, du coup il faut vérifier&hellip; à chaque fois?<br />
			Euh&hellip; Oui !
		</p>

	</Slide>

	<Slide>
		<h3>Notre objectif aujourd’hui</h3>
		<p class="fragment">Explorer des moyens pour éviter d'avoir à se poser ce genre de questions</p>
		<p class="fragment">En utilisant le typage et la structure des données</p>
		<p class="fragment">Pour un code plus explicite, et plus simple à maintenir</p>

	</Slide>

	<Slide>
		<h3>Mise en garde</h3>
		<p style="font-size: 1.5em;">Ceci n'est pas une conférence sur <span
			style="text-decoration: line-through">le cyclimse</span> les tests !
		</p>
	</Slide>
</section>
