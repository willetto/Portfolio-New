<script>
	import ComingSoon from '$lib/modules/coming-soon.svelte';
	import HeroHome from '$lib/modules/hero-home.svelte';
	import Skills from '$lib/modules/skills.svelte';
</script>

<HeroHome />
<ComingSoon />
<Skills />

<style>
	:root {
		scroll-behavior: smooth;
		overscroll-behavior: contain;
	}
</style>
