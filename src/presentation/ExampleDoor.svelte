<script>
	import Slide from '$lib/Slide.svelte';
	import PseudoCode from '$lib/PseudoCode.svelte';
	import doorImage from './assets/images/door.png';
	import Code from '$lib/Code.svelte';
	import no from './assets/images/no.gif';
	import godNo from './assets/images/godno.gif';
	import yes from './assets/images/yes.gif';
	import LanguageLogo from './LanguageLogo.svelte';

	const doorExample = {
		naiveType: `
type Door = { isClosed: Boolean; isLocked: Boolean }`,
		naiveInstances: `
const door1: Door = { isClosed: false, isLocked: false }
const door2: Door = { isClosed: true, isLocked: false }
const door3: Door = { isClosed: false, isLocked: true }
const door4: Door = { isClosed: true, isLocked: true }`,
		betterType: `
type Door =
    { state: "open" } |
    { state: "closed"; locked: Boolean }`,
		betterInstances: `
const door1: Door = { state: "open" }
const door2: Door = { state: "closed", locked: false }
const door3: Door = { state: "closed", locked: true }`
	};
</script>

<style>
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
	<p>
		<img src={doorImage} alt="Une porte" />
	</p>
	<p>3 états:</p>
	<p>
		Ouverte<br />
		Fermée<br />
		Fermée et verrouillée
	</p>
</Slide>


<Slide>
	<PseudoCode>
		{`
type Door = { isClosed: Boolean; isLocked: Boolean }
`}
	</PseudoCode>
	<div class="fragment">
		<p>&darr;</p>
		<PseudoCode>
			{`
door1 = { isClosed: False, isLocked: False }
door2 = { isClosed: Frue, isLocked: False }
door3 = { isClosed: False, isLocked: True }
door4 = { isClosed: True, isLocked: True }`}
		</PseudoCode>
	</div>
	<div class="fragment">
		<p>&darr;</p>
		<p>4 états représentables</p>
	</div>
	<p class="fragment">
		<img src="{no}" alt="no" class="react" />
	</p>
</Slide>

<Slide>
	<PseudoCode>
		{`
type Door = { state: "open" | "closed"; isLocked?: Boolean }
`}
	</PseudoCode>
	<div class="fragment">
		<p>&darr;</p>
		<PseudoCode>
			{`
door1 = { state: "open" }
door2 = { state: "closed", isLocked: False }
door3 = { state: "closed", isLocked: True }`}
		</PseudoCode>
	</div>
	<div class="fragment">
		<PseudoCode>
			{`
door4 = { state: "open", isLocked: False }
door5 = { state: "open", isLocked: True }
door6 = { state: "closed" }`}
		</PseudoCode>
	</div>
	<div class="fragment">
		<p>&darr;</p>
		<p>6 états représentables</p>
	</div>
	<p class="fragment">
		<img src="{godNo}" alt="god no" class="react" />
	</p>
</Slide>

<Slide>
	<PseudoCode>
		{`
type OpenDoor = { state: "open" }
type ClosedDoor = { state: "closed", isLocked: Boolean }
type Door = OpenDoor | ClosedDoor
`}
	</PseudoCode>
	<div class="fragment">
		<p>&darr;</p>
		<PseudoCode>
			{`
door1 = { state: "open" }
door2 = { state: "closed", isLocked: False }
door3 = { state: "closed", isLocked: True }`}
		</PseudoCode>
	</div>
	<div class="fragment">
		<p>&darr;</p>
		<p>3 états représentables</p>
	</div>
	<p class="fragment">
		<img src="{yes}" alt="yes" class="react" />
	</p>
</Slide>

<Slide>
	<LanguageLogo language="java" />
	<Code language="java">
		{`
// Types
sealed interface Door permits OpenDoor, ClosedDoor {}
record OpenDoor() implements Door {}
record ClosedDoor(boolean isLocked) implements Door {}

// Usage
Door door1 = new OpenDoor();
Door door2 = new ClosedDoor(true);
Door door3 = new ClosedDoor(false);`}
	</Code>

	<p class="warning">
		<code>record</code> et <code>sealed</code> nécessitent Java 17 (cf. <a
		href="https://openjdk.org/jeps/395" target="_blank">JEP 395</a> + <a
		href="https://openjdk.org/jeps/409" target="_blank">JEP 409</a>)
	</p>
</Slide>

<Slide>
	<LanguageLogo language="typescript" />
	<Code language="typescript">
		{`
// Types
type OpenDoor = { state: "open" }
type CloseDoor = { state: "closed", isLocked: boolean }
type Door = OpenDoor | CloseDoor

// Usage
const door1: Door = { state: "open" };
const door2: Door = { state: "closed", isLocked: false };
const door3: Door = { state: "closed", isLocked: true };`}
	</Code>
</Slide>

<Slide>
	<LanguageLogo language="python" />
	<Code language="python">
		{`
# Types
@dataclass
class OpenDoor:
		pass

@dataclass
class CloseDoor:
    is_locked: bool

type Door = OpenDoor | CloseDoor

# Usage
door1: Door = OpenDoor()
door2: Door = CloseDoor(is_locked=False)
door3: Door = CloseDoor(is_locked=True)`}
	</Code>

	<p class="warning">
		Mot clé <code>type</code> nécessite Python 3.12 (cf. <a
		href="https://peps.python.org/pep-0695/"
		target="_blank">PEP 695</a>)
	</p>
</Slide>
