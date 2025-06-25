<script lang="ts">
	interface Props {
		language: 'python' | 'java' | 'typescript';
	}

	const { language }: Props = $props();
</script>

<style lang="css">
  div {
    position: absolute;
    right: 0;
    top: calc(50% - 1.5rem - 10px);

    i {
      font-size: 1.5em;
      color: var(--r-heading-color);
      border: 5px solid var(--r-heading-color);
      background: #feeee0;
      border-radius: 50%;
      padding: 10px;
    }
  }
</style>

<div>
	<i class="devicon-{language}-plain"></i>
</div>
