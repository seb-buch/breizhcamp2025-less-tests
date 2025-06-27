<script>
	import Slide from '$lib/Slide.svelte';
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

	</Slide>

	<Slide>
		<p>
			Tous les langages de programmation utilisent un système de règles pour<br />
			<b>définir et gérer les types de données</b>
		</p>
		<p>
			Il existe différentes approches que peuvent implémenter les langages de programmation
		</p>


	</Slide>

	<Slide>
		<h3>Typage statique vs dynamique</h3>

		<p><b>Statique</b>&nbsp;: les erreurs de type sont détectées à la compilation</p>
		<p><b>Dynamique</b>&nbsp;: les erreurs de type sont détectées à l’exécution</p>


	</Slide>

	<Slide>
		<h3>Typage nominal vs structurel</h3>

		<p><b>Nominal</b>&nbsp;: les types sont définis par leur nom</p>
		<p><b>Structurel</b>&nbsp;: les types sont définis par leur structure</p>


	</Slide>

	<Slide>
		<h3 style="padding-bottom: 1em">Exemples</h3>

		<table>
			<thead>
			<tr>
				<td>Typage</td>
				<th>Nominal</th>
				<th>Structurel</th>
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

	</Slide>


</Slide>
