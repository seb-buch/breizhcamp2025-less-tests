<script>
	import Slide from '$lib/Slide.svelte';
	import SpeakerNotes from '$lib/SpeakerNotes.svelte';
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

		<SpeakerNotes>
Les tests font partie de notre quotidien.

Ils nous permettent:

 - de garantir la qualité du code
 - de vérifier les cas limites de prévenir les erreurs
 - d’accompagner l’évolution du logiciel.

Bref, Ils constituent un outil *fondamental*, on est d’accord.
	</SpeakerNotes>
	</Slide>


	<Slide>
		<h3>Mais soyons honnêtes&nbsp;&hellip;</h3>
		<p>Écrire des tests, ce n’est pas toujours fun 😅</p>
		<p class="fragment">On est souvent obligé de couvrir des cas liés à des données erronées </p>
		<p class="fragment">Parfois, on écrit des tests... juste pour éviter un bug improbable</p>

		<SpeakerNotes>
Mais soyons honnêtes deux minutes :

 - Premièrement, écrire des tests, ce n’est pas toujours passionnant.
 - Ensuite, on se sent souvent obligé de couvrir des cas qui, au fond, nous semblent un peu absurdes.
 - Et parfois, on se dit : 'Bon, allez, je vais tester quand même ce cas bizarre…'

	</SpeakerNotes>
	</Slide>

	<Slide>
		<h3>Quelques exemples</h3>
		<p class="fragment" >Et si la <code>quantity</code> est négative&nbsp;?</p>
		<p class="fragment">Et si <code>user.age</code> n’est pas un entier&nbsp;?</p>
		<p class="fragment" >
			Normalement, <code>[nom attribut]</code> est défini si <code>[nom autre attribut]</code> est défini.<br/>
			Euh&hellip; T'es sûr&nbsp;?<br/>
			Normalement&hellip;<br/>
			Ben, du coup il faut vérifier.<br/>
			Euh&hellip; Oui !

		<SpeakerNotes>
Je vous propose quelques exemples pour illustrer ça.

On commence par un test qui va parler à ceux qui font du Java.
Le fameux test dit du "il se passe quoi si ma variable a une valeur `null`?"

Mais, je pourrais parler du test de protection contre "l'utilisateur qui veut commander -3 paires de chaussures"

Ou bien le test de non-régression parce que "une fois, on s'est tapé une erreur 500 en prod parce qu'on peut créer un utilisateur avec un age qui est une string"

Bref, on passe beaucoup de temps à écrire des tests juste pour éviter ce genre de bugs…

Et si je vous disais qu'on peut éviter ce genre de bug sans avoir besoin de faire d'écrire plein de tests?
	</SpeakerNotes>
	</Slide>

	<Slide>
		<h3>Notre objectif aujourd’hui</h3>
		<p class="fragment">Explorer des moyens pour éviter d'avoir à se poser ce genre de questions</p>
		<p class="fragment">En utilisant le typage et la structure des données</p>
		<p class="fragment">Pour un code plus explicite, et plus simple à maintenir</p>

		<SpeakerNotes>
C'est ce que je vous propose de voir ensemble pendant ces 3/4 d'heure qu'on va passer ensemble.

Pour cela, on va commencer par s'intéresser un peu aux différentes approches de typage des données prises par les languages de programmation.

On verra ensuite concrètement comment utiliser un typage de données adapté pour obtenir un code plus robuste et plus simple à maintenir.
Afin qu'un maximum de personnes trouvent leur compte, on prendra comme exemples trois languages très utilisés: Java, Typescript, et Python.
	</SpeakerNotes>
	</Slide>

	<Slide>
		<h3>Mise en garde</h3>
			<p class="fragment">On ne va pas parler de types de tests&nbsp;: unitaires, intégration, end-to-end,
				utilisateurs…
			</p>
			<p class="fragment">On parle des tests au sens large&nbsp;: un moyen de détecter des anomalies
			</p>
			<p class="fragment">On n'en verra pas&nbsp;!</p>

		<SpeakerNotes>
Avant d'aller plus loin, on petit avertissement pour les puristes de la terminologie capablent de discuter longtemps (trop longtemps) pour savoir si tel ou tel test est un test unitaire ou bien d'intégration.

Ici, je vais parler de tests au sens large.

Pour ce qui nous intéresse aujourd'hui, un test est un moyen de détecter des anomalies (idéalement le plus tôt possible)
	</SpeakerNotes>
	</Slide>
</section>
