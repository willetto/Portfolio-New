<script>
	import SkillItem from './fruit-label.svelte';
	import astro from '$lib/imgs/icons/astro.svg';
	import css from '$lib/imgs/icons/css.svg';
	import d3 from '$lib/imgs/icons/d3.svg';
	import patreon from '$lib/imgs/icons/patreon.svg';
	import shopify from '$lib/imgs/icons/shopify.svg';
	import storyblok from '$lib/imgs/icons/storyblok.svg';
	import svelte from '$lib/imgs/icons/svelte.svg';
	import ts from '$lib/imgs/icons/ts.svg';
	import vue from '$lib/imgs/icons/vue.svg';
	import wp from '$lib/imgs/icons/wp.svg';
</script>

<div class="skills-wrapper">
	<div class="skills-header"></div>
	<div class="skills-list">
		<SkillItem svg={shopify} color="#95bf47" shape="oblong" angle={10} title="Shopify" />
		<SkillItem svg={svelte} color="#FC2506" shape="oval" angle={-15} title="Svelte" />
		<SkillItem svg={wp} color="#1C6189" shape="square" angle={5} title="WordPress" />
		<SkillItem svg={astro} color="#FF5D01" shape="oval" angle={-5} title="Astro" />
		<SkillItem svg={css} color="rebeccapurple" shape="round" title="CSS" />
		<SkillItem svg={d3} color="#F7931E" shape="square" angle={10} title="D3" />
		<SkillItem svg={patreon} color="#000" shape="oval" angle={10} title="Patreon" />
		<SkillItem svg={storyblok} color="#09B3AF" shape="square" angle={-10} title="Storyblok" />
		<SkillItem svg={ts} color="#3178C6" shape="square" angle={10} title="TypeScript" />
		<SkillItem svg={vue} color="#4FC08D" shape="oval" title="Vue" />
	</div>
</div>

<style>
	.skills-wrapper {
		display: grid;
		place-items: center;
		padding: 5rem 3rem;
	}
	.skills-list {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		justify-content: center;

		width: 100%;
		/* max-width: 800px; */
	}
</style>
