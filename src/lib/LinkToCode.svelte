<script lang="ts">
	type Props = {
		url?: string,
		text?: string,
	}

	const { url, text = 'Code' }: Props = $props();

</script>

<style>
  .reset {
    color: black;
    padding: 0 0.5em;
  }
</style>

<p class="link-to-code">
	{#if url === undefined}
		<span class="reset">⚠️</span>
		{text}
		<span class="reset">⚠️</span>
	{:else }
		<a href={url} aria-label="Aller vers le code" target="_blank">
			{text}
		</a>
	{/if}
</p>
