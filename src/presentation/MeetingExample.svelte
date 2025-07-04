<script>
	import Slide from '$lib/Slide.svelte';
	import Code from '$lib/Code.svelte';
	import meetingIllustration from './assets/images/meetingExample.png';
	import VerticalSpacer from '$lib/VerticalSpacer.svelte';
	import smart from './assets/images/smart.gif';
	import LinkToCode from '$lib/LinkToCode.svelte';
</script>

<style lang="css">
  .example-logic {
    display: flex;
    flex-direction: row;
    justify-content: center;

    img {
      height: 400px;
      border-radius: 1em;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
    }

    & > div {
      padding: 0 1em;
    }

    & > div:nth-child(3) {
      text-align: left;
    }
  }

  .object {
    color: #a46e2d;
    font-weight: bold;
  }

  .transfo {
    color: #8a8787;
  }
</style>


<Slide>
	<h3>Gestion de réunions</h3>
	<div class="example-logic">
		<div>
			<img src={meetingIllustration} alt="illustration app meeting" />
		</div>
		<div>
			<p class="object">JSON</p>
			<p class="transfo fragment" data-fragment-index="1">↓</p>
			<p class="object fragment" data-fragment-index="1"><code>MeetingFramework</code></p>
			<p class="transfo fragment" data-fragment-index="2">↓</p>
			<p class="object fragment" data-fragment-index="2"><code>Meeting</code></p>
		</div>
		<div>
			<p class="object">object "brut"</p>
			<p class="transfo fragment" data-fragment-index="1">framework</p>
			<p class="object fragment" data-fragment-index="1">objet validé structurellement</p>
			<p class="transfo fragment" data-fragment-index="2">constructeur</p>
			<p class="object fragment" data-fragment-index="2">objet métier validé</p>
		</div>
	</div>

	<aside class="notes">
		Ce schéma montre clairement que chaque étape a son rôle. L’objet brut est prévalidé via un
		schéma Zod, puis transformé en un objet métier via des constructeurs intelligents qui
		appliquent
		la logique métier.
	</aside>
</Slide>

<Slide>
	<h3>Exemples de JSON "bruts"</h3>
	<Code language="json" lineNumbers={null}>
		{`
{
	"type": "in_person",
	"title": "Réunion trimestrielle",
	"contactEmail": "alice.morgan@acme.org",
	"meetingRoom": "small",
	"nGuests": 10
}`}
	</Code>
	<Code language="json" lineNumbers={null}>
		{`
{
  "type": "online",
  "title": "Weekly Sync-up",
  "contactEmail": "jane.doe@acme.org",
  "videoPlatform": "meet",
  "videoLink": "https://meet.google.com/abc-defg-hij"
}`}
	</Code>
</Slide>

<Slide>
	<h3>Étape 1 : Conversion via le framework</h3>
	<ol>
		<li>conversion JSON &rarr; objet valide</li>
		<li>
			conversion des salles au format internes:<br />
			"small" &rarr; "Room 101" <br />
			"medium" &rarr; "Room 42" <br />
			"large" &rarr; "Amphitheater"
		</li>
		<li><b>validation structurelle</b></li>
	</ol>

	<LinkToCode text="Code en Java"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/java/src/main/java/sbuch/presentation/examples/meeting/framework/MeetingFramework.java" />
	<LinkToCode text="Code en Typescript"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/typescript/src/meetingExample/framework.ts" />
	<LinkToCode text="Code en Python"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/python/src/examples/meeting/framework.py" />

	<p class="fragment">
		Pas besoin de test si c'est le framework qui teste !
		<img src={smart} alt="smart" style="height: 3em; vertical-align: middle;padding-left: 1em" />
	</p>
</Slide>


<Slide>
	<h3>Étape 2 : Création des objets métiers</h3>
	<p>Prise en compte des règles métiers:</p>
	<ul>
		<li><b>Email:</b> <code>firstname.lastname@acme.org</code></li>
		<li>
			<b>Salle de réunions:</b><br />
			"Room 101" &rarr; capacité max: 10<br />
			"Room 42" &rarr; capacité max: 50<br />
			"Amphitheater" &rarr; capacité max: 200
		</li>
	</ul>

	<VerticalSpacer height="1em" />

	<LinkToCode text="Code en Java"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/java/src/main/java/sbuch/presentation/examples/meeting/core/Meeting.java" />
	<LinkToCode text="Code en Typescript"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/typescript/src/meetingExample/core.ts" />
	<LinkToCode text="Code en Python"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/python/src/examples/meeting/core.py" />
</Slide>

<Slide>
	<h3>Etape 3 : On utilise des objets validés!</h3>
	<VerticalSpacer height="2em" />

	<LinkToCode text="Code en Java"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/java/src/main/java/sbuch/presentation/examples/meeting/MeetingExample.java" />
	<LinkToCode text="Code en Typescript"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/typescript/src/meetingExample/meetingExample.ts" />
	<LinkToCode text="Code en Python"
							url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/python/src/examples/meeting/meeting_example.py" />
</Slide>
