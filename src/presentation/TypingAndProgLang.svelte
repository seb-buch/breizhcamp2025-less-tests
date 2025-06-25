<script>
	import Slide from '$lib/Slide.svelte';
	import SpeakerNotes from '$lib/SpeakerNotes.svelte';
</script>

<style>
  h3 {
    padding-bottom: 1.5em;
  }

  p {
    line-height: 1.6;
    margin-bottom: 1.5em;
  }

  table {
    caption-side: bottom;

    th, td {
      padding: 1.2em;
      text-align: center;
      border-bottom: none;
    }

    th {
      color: var(--r-heading-color);
      font-family: var(--r-heading-font), sans-serif;
    }

    caption {
      font-size: 0.5em;
      padding-top: 0.5em;
    }

    thead td {
      opacity: 0.5;
      font-family: var(--r-heading-font), sans-serif;

    }
  }
</style>

<Slide>
	<Slide>
		<h2>
			Langages de progammation<br>
			et
			systèmes de typage
		</h2>

		<SpeakerNotes>
			[A REVOIR]
Pour comprendre comment le typage peut nous aider, il faut déjà clarifier ce qu’on met derrière le mot 'typage'…
		</SpeakerNotes>
	</Slide>

	<Slide>
		<p>
			Tous les langages de programmation utilisent un système de règles pour<br />
			<b>définir et gérer les types de données</b>
		</p>
		<p>
			Il existe différentes approches que peuvent implémenter les languages de programmation
		</p>

		<SpeakerNotes>
			[A REVOIR]
Le typage, c’est un outil super puissant.
Il nous permet de détecter des erreurs dès l’écriture du code, avant même de lancer le programme.
Il nous guide dans la conception des systèmes, et il réduit la surface des bugs.
Mais... tous les langages ne jouent pas dans la même cour.
		</SpeakerNotes>
	</Slide>

	<Slide>
		<h3>Typage statique vs dynamique</h3>

		<p><b>Statique</b>&nbsp;: les erreurs de type sont détectées à la compilation</p>
		<p><b>Dynamique</b>&nbsp;: les erreurs de type sont détectées à l’exécution</p>

		<SpeakerNotes>
Premier axe : statique ou dynamique.
En statique, comme en Java ou Rust, le compilateur va vérifier les types avant même d’exécuter le code.
En dynamique, comme en Python ou JavaScript, on ne le saura… qu’au moment de l’exécution.
Chacun a ses avantages et ses inconvénients.
		</SpeakerNotes>
	</Slide>

	<Slide>
		<h3>Typage nominal vs structural</h3>

		<p><b>Nominal</b>&nbsp;: les types sont définis par leur nom (ou leur "étiquette")</p>
		<p><b>Structural</b>&nbsp;: les types sont définis par leur structure</p>

		<SpeakerNotes>
Premier axe : statique ou dynamique.
En statique, comme en Java ou Rust, le compilateur va vérifier les types avant même d’exécuter le code.
En dynamique, comme en Python ou JavaScript, on ne le saura… qu’au moment de l’exécution.
Chacun a ses avantages et ses inconvénients.
		</SpeakerNotes>
	</Slide>

	<Slide>
		<h3 style="padding-bottom: 1em">Exemples</h3>

		<table>
			<thead>
			<tr>
				<td>Typage</td>
				<th>Nominal</th>
				<th>Structural</th>
			</tr>
			</thead>
			<tbody>
			<tr>
				<th>Statique</th>
				<td>Java, C#, Rust, Kotlin</td>
				<td>TypeScript, Go</td>
			</tr>
			<tr>
				<th>Dynamique</th>
				<td>PHP</td>
				<td>Python, JavaScript</td>
			</tr>
			</tbody>
			<caption>
				<a href="https://en.wikipedia.org/wiki/Comparison_of_programming_languages_by_type_system"
					 target="_blank">
					Source plus complète
				</a>
			</caption>
		</table>

		<SpeakerNotes>
Pour résumer tout ça, voilà un tableau qui croise ces deux axes :
Statique ou dynamique d’un côté, nominal ou structural de l’autre.
Quelques exemples de langages célèbres pour chaque case :
		</SpeakerNotes>
	</Slide>


</Slide>
