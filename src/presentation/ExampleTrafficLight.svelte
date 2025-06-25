<script>
	import Slide from '$lib/Slide.svelte';
	import PseudoCode from '$lib/PseudoCode.svelte';
	import Code from '$lib/Code.svelte';
	import TrafficLight from './assets/images/traffic_light.png';
	import LanguageLogo from './LanguageLogo.svelte';
	import nope from './assets/images/no.gif';
	import yes from './assets/images/yes.gif';
</script>

<style>
  .illustration {
    img {
      border-radius: .5em;
      box-shadow: 0 0 10px #40404088;
    }

  }

  .type1, .type2, .type3, .logic-operand {
    font-family: var(--code-font-family), monospace;
  }

  .type1 {
    color: #e35238;
  }

  .type2 {
    color: #75b620;
  }

  .type3 {
    color: #3290d9;
  }

  .logic-operand {
    padding-left: 0.5ch;
  }

  .logic-text {
    font-family: serif;
    line-height: 2em;

    background: rgba(255, 253, 253, 0.5);
    border-radius: 0.2em;
    padding: 0.5em 1em;
    width: fit-content;
    margin: auto;
  }

  .warning {
    &:before {
      content: "⚠️";
      padding-right: 0.2em;
    }

    padding-top: 1em;
  }

  .react {
    height: 6em;
  }

</style>


<Slide>
	<p class="illustration">
		<img src={TrafficLight} alt="Feu de circulation" />
	</p>
	<PseudoCode isFragment>
		{`
TrafficLight = (Boolean, Boolean, Boolean)`}
	</PseudoCode>
	<PseudoCode isFragment>
		{`
TrafficLightColor = String`}
	</PseudoCode>
	<PseudoCode isFragment>
		{`
TrafficLightColor = "red" | "orange" | "green"`}
	</PseudoCode>
</Slide>

<Slide>
	<LanguageLogo language="java" />
	<Code language="java" lineNumbers={null}>
		{`
// TrafficLight = (Boolean, Boolean, Boolean)
record TrafficLight(Boolean redOn,
										Boolean orangeOn,
										Boolean greenOn) {
}

// TrafficLightColor = String
// Use String

// TrafficLightColor = "red" | "orange" | "green"
enum TrafficLightColor {RED, ORANGE, GREEN}`}
	</Code>

	<p class="warning">
		<code>record</code> nécessite Java 17 (cf. <a href="https://openjdk.org/jeps/395"
																									target="_blank">JEP 395</a>)
	</p>

</Slide>

<Slide>
	<LanguageLogo language="typescript" />
	<Code language="typescript" lineNumbers={null}>
		{`
// TrafficLight = (Boolean, Boolean, Boolean)
type TrafficLight = [boolean, boolean, boolean]

// TrafficLightColor = String
type TrafficLightColor = string

// TrafficLightColor = "red" | "orange" | "green"
type TrafficLightColor = "red" | "orange" | "green"`}
	</Code>

</Slide>

<Slide>
	<LanguageLogo language="python" />
	<Code language="python" lineNumbers={null}>
		{`
# TrafficLight = (Boolean, Boolean, Boolean)
type TrafficLight = tuple[bool, bool, bool]

# TrafficLightColor = String
type TrafficLightColor = str

# TrafficLightColor = "red" | "orange" | "green"
type TrafficLightColor = Literal["red", "orange", "green"]`}
	</Code>

	<p class="warning">
		Mot clé <code>type</code> nécessite Python 3.12 (cf. <a
		href="https://peps.python.org/pep-0695/"
		target="_blank">PEP 695</a>)
	</p>
</Slide>


<Slide>
	<PseudoCode>
		{`
TrafficLight = (Boolean, Boolean, Boolean)`}
	</PseudoCode>
	<div class="fragment">
		<p>&darr;</p>
		<p class="logic-text">
			Boolean = &lbrace;<i>True</i>, <i>False</i>&rbrace;
			<br />
			TrafficLight = &lbrace;(
			<span class="type1">x</span>,
			<span class="type2">y</span>,
			<span class="type3">z</span> ):
			<span class="type1">x</span> &in; Boolean,
			<span class="type2">y</span> &in; Boolean,
			<span class="type3">z</span> &in; Boolean;
			&rbrace;
		</p>
	</div>
	<div class="fragment">
		<p>&darr;</p>
		<p>
			<span class="type1">2</span><span class="logic-operand">&times;</span>
			<span class="type2">2</span><span class="logic-operand">&times;</span>
			<span class="type3">2</span>
			&equals; 8 valeurs/états possibles
		</p>
	</div>
	<p class="fragment">
		<img src={nope} alt="not good" class="react" />
	</p>
</Slide>

<Slide>
	<PseudoCode>
		{`
			TrafficLightColor = String`}
	</PseudoCode>
	<div class="fragment">
		<p>&darr;</p>
		<p class="logic-text">
			TrafficLightColor = &lbrace;
			<span class="type1">x</span> :
			<span class="type1">x</span> &in;
			&lbrace; "red", "orange", "green", "", "Aa@1", &hellip; &rbrace;
			&rbrace;
		</p>
	</div>
	<div class="fragment">
		<p>&darr;</p>
		<p>
			"infinité" de valeurs/états possibles
		</p>
	</div>
</Slide>

<Slide>
	<PseudoCode>
		{`
			TrafficLightColor = "red" | "orange" | "green"`}
	</PseudoCode>
	<div class="fragment">
		<p>&darr;</p>
		<p class="logic-text">
			TrafficLightColor = &lbrace;
			<span class="type1">x</span> :
			<span class="type1">x</span> &in;
			&lbrace; "red", "orange", "green" &rbrace;
			&rbrace;
		</p>
	</div>
	<div class="fragment">
		<p>&darr;</p>
		<p>
			3 valeurs/états possibles
		</p>
	</div>
	<p class="fragment">
		<img src={yes} alt="good" class="react" />
	</p>
</Slide>
