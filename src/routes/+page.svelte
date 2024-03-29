<script>
	import Analytics from '$lib/modules/analytics.svelte';
	import ComingSoon from '$lib/modules/coming-soon.svelte';
	import HeroHome from '$lib/modules/hero-home.svelte';
</script>

<Analytics />

<HeroHome />
<ComingSoon />

<style>
	:root {
		scroll-behavior: smooth;
		overscroll-behavior: contain;
	}
</style>
