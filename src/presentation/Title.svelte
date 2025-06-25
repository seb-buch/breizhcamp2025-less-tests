<script>
	import Slide from '$lib/Slide.svelte';
	import logo from './assets/images/logo_breizhcamp.png';
	import VerticalSpacer from '$lib/VerticalSpacer.svelte';
</script>

<style lang="css">

  .logo-conf {
    text-align: right;

    & img {
      vertical-align: middle;
    }

    font-size: 0.7em;
    color: #000;
  }

</style>

<Slide>
	<h1>
		Le meilleur test, c'est celui<br />
		qu'on n'a pas à écrire!
	</h1>
	<h3>Sébastien Buchoux</h3>
	<VerticalSpacer height="5em" />
	<p class="logo-conf">
		<img src={logo} alt="logo conf" />
		&nbsp;&ndash;&nbsp;
		25-27 juillet 2025
	</p>
</Slide>
