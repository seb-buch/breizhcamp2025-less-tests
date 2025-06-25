<script>
	import Slide from '$lib/Slide.svelte';
	import Code from '$lib/Code.svelte';
	import duckIllustration from './assets/images/duck-example.png';
	import LanguageLogo from './LanguageLogo.svelte';
	import LinkToCode from '$lib/LinkToCode.svelte';
</script>

<style>
  h3 {
    background: rgba(255.0, 252.0, 250, 0.8);
    backdrop-filter: blur(5px);
    border-radius: .2em;
  }
</style>

<section>
	<Slide>
		<h2>Typage en action</h2>
	</Slide>
	<Slide backgroundImage="{duckIllustration}" backgroundSize="cover">
		<h3>
			C'est l'histoire d'un canard qui fait ...
		</h3>
	</Slide>

	<Slide>
		<LanguageLogo language="java" />
		<Code language="java">
			{`
interface Quacker {
    String quack();
}

// True quackers
class Duck implements Quacker {...}
class BabyDuck extends Duck {...}
class RubberDuck implements Quacker {...}

// Structural quacker
class FreckledDuck {
    public String quack() {...}
}

// Not a quacker
class Dog {
    public String woof() {...}
}
			`}
		</Code>
	</Slide>
	<Slide>
		<LanguageLogo language="java" />
		<Code language="java">
			{`
// Uses class
void makeDuckQuack(Duck duck) {...}

// Uses interface
void makeQuackerQuack(Quacker quacker) {...}

// Uses introspection
void makeStuffQuack(Object maybeQuacker) {...}
			`}
		</Code>
		<LinkToCode />
	</Slide>

	<Slide>
		<LanguageLogo language="typescript" />
		<Code language="typescript">
			{`
interface Quacker {
    quack(): string;
}

// True quackers
class Duck implements Quacker {...}
class BabyDuck extends Duck {...}
class RubberDuck implements Quacker {...}

// Structural quacker
class FreckledDuck {
    public quack(): string {...}
}

// Not a quacker
class Dog {
    public woof(): string {...}
}
			`}
		</Code>
	</Slide>

	<Slide>
		<LanguageLogo language="typescript" />
		<Code language="typescript">
			{`
// Uses class... or does it?
function makeDuckQuack(duck: Duck) {...}

// Uses introspection
function makeStuffQuack(stuff: unknown) {...}
		`}
		</Code>
		<LinkToCode />
	</Slide>

	<Slide>
		<LanguageLogo language="python" />
		<Code language="python">
			{`
class Quacker(Protocol):
    def quack(self) -> str: ...

# True quackers
class Duck(Quacker):
    def quack(self) -> str: ...
class BabyDuck(Duck):
    def quack(self) -> str: ...
class RubberDuck(Quacker):
    def quack(self) -> str: ...

# Structural quacker
class FreckledDuck:
    def quack(self) -> str: ...

# Not a quacker
class Dog:
    def woof(self) -> str: ...
			`}
		</Code>
	</Slide>

	<Slide>
		<LanguageLogo language="python" />
		<Code language="python">
			{`
# Uses class
def make_duck_quack(duck: Duck) -> None: ...

# Uses interface
def make_quacker_quack(quacker: Quacker) -> None: ...

# No static code analysis because of Any
def make_stuff_quacks_bad(stuff: Any) -> None: ...

# Uses introspection "Look Before You Leap"-style
def make_stuff_quacks_lbyl(stuff: object) -> None: ...

# Same with "Easier to Ask Forgiveness than Permission"-style
def make_stuff_quacks_eafp(stuff: object) -> None:...
`}
		</Code>
		<LinkToCode
			url="https://github.com/seb-buch/more-types-less-tests-code/blob/main/python/src/examples/duck_example.py" />
	</Slide>

</section>
