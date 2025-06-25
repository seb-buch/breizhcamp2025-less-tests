<script lang="ts">
	import type { Snippet } from 'svelte';

	interface Props {
		isFragment?: true | undefined;
		fragmentId?: string;
		children: Snippet;
	}

	let {
		children,
		isFragment,
		fragmentId
	}: Props = $props();

</script>

<style>
  .code-block {
    position: relative;

    pre {
      /*max-width: 90%;*/
      font-size: 1.0em;
      box-shadow: none;

      code {
        background: rgba(255, 253, 253, 0.6);
        padding: .2em;
        border-radius: .2em;
      }

    }

  }
</style>

{#if children}
	<div class="code-block">
		<pre class="language-typescript {isFragment ? 'fragment':''}" style="width:fit-content"
				 data-fragment-index={fragmentId}>
			<code data-noescape data-trim>
				{@render children()}
			</code>
		</pre>
	</div>
{/if}
