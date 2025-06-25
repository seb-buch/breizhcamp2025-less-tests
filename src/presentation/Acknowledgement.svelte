<script>
	import Slide from '$lib/Slide.svelte';
	import qrCodeFeedback from './assets/images/QRcode_feedback.svg';
	import qrCodeProfile from './assets/images/QRcode_github.svg';
</script>

<style>
  div {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    h1 {
      flex-grow: 1;
    }

    figure {
      padding: 0 5rem;

      img {
        height: 20rem;
      }
    }
  }
</style>
<Slide>
	<div>
		<figure>
			<img src={qrCodeProfile} alt="QR code diapos" />
			<figcaption>Diapos et code</figcaption>
		</figure>
		<h1>
			Merci
		</h1>
		<figure>
			<img src={qrCodeFeedback} alt="QR code Feedback" />
			<figcaption>Feedback</figcaption>
		</figure>
	</div>
</Slide>
