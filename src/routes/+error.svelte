<script>
	import kermit from '$lib/imgs/kermit.webp';
	import { page } from '$app/stores';
</script>

<div class="page-wrapper">
	<div class="error-wrapper">
		<h1 class="h1">{$page.status}: {$page.error.message}</h1>
		<img src={kermit} alt="kermit is lost" />
		<a class="p" href="/">Back to the home page.</a>
	</div>
</div>

<style>
	:root {
		background-color: var(--c-green-600);
	}
	.page-wrapper {
		display: grid;
		place-items: center;
		height: 100vh;
	}

	.error-wrapper {
		display: flex;
		flex-direction: column;
		gap: 1rem;
		align-items: center;
	}
	img {
		width: 100%;
		max-width: 300px;
		border-radius: 3px;
	}
	a {
		color: var(--c-yellow-700);
		text-decoration: none;
		transition:
			color 0.2s ease-in-out,
			font-style 0.2s ease-in-out;
	}
	a:hover,
	a:focus {
		font-style: italic;
		color: var(--c-green-700);
	}
</style>
