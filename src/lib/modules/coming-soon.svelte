<script lang="ts">
	import garden from '$lib/imgs/garden-bg.jpg';
	import Cards from './cards.svelte';

	let scroll = $state(0);
	let parallaxElement = $state<HTMLElement | null>(null);

	// Calculate parallax based on element position with clamping
	const parallaxStyle = $derived(() => {
		if (!parallaxElement) return '';

		// Add scroll as a dependency to trigger recalculation
		const _ = scroll;

		const elementTop = parallaxElement.getBoundingClientRect().top;
		const elementHeight = parallaxElement.offsetHeight;
		const maxParallax = elementHeight * 0.5; // Max 30% of element height
		const parallaxOffset = Math.max(-maxParallax, Math.min(0, elementTop * -0.1));

		console.log('Parallax debug:', { elementTop, elementHeight, maxParallax, parallaxOffset });

		return `transform: translateY(${parallaxOffset}px);`;
	});
</script>

<svelte:window bind:scrollY={scroll} />

<div class="coming-soon-wrapper">
	<div class="background parallax" bind:this={parallaxElement}>
		<img src={garden} alt="" style={parallaxStyle()} />
	</div>
	<div class="center">
		<h2 class="h2">Welcome!</h2>
		<p class="p">
			I'm currently overhauling my site. In the meantime, here are a few links to my recent work.
		</p>
		<p class="p">
			<a href="mailto:trey.willetto@gmail.com" class="link" target="_blank">
				Feel free to drop me a line!
			</a>
		</p>
		<Cards />
	</div>
</div>

<style>
	.coming-soon-wrapper {
		--local-bg-color: var(--c-white);
		--local-font-color: var(--c-white);
		--local-bg-opacity: 0.4;

		position: relative;
		z-index: 0;

		overflow: hidden;
		display: flex;
		flex-direction: column;
		align-items: center;

		min-block-size: 70vh;
		padding: 5rem 3rem;

		color: var(--local-font-color);

		background-color: var(--local-bg-color);
		/* background-image: var(--texture-url); */
		background-repeat: no-repeat;
		background-size: cover;
		&::before {
			/* Drop Shadow */
			pointer-events: none;
			content: '';

			position: absolute;
			z-index: -1;
			top: -1.5rem;
			left: 0;

			width: 100%;
			height: 2.5rem;

			opacity: 0.4;
			background-image: linear-gradient(180deg, var(--c-black) 0%, transparent 98% 0);
			mix-blend-mode: multiply;
		}

		&::after {
			/* BG Image */
			pointer-events: none;
			content: '';

			position: absolute;
			z-index: -1;
			top: 0;
			left: 0;

			width: 100%;
			height: 100%;

			opacity: var(--local-bg-opacity);
			background-color: var(--c-black);
			mix-blend-mode: multiply;

			transition: opacity 0.3s ease-in-out;
		}
	}
	.background {
		position: absolute;
		z-index: -2;
		inset: 0;
		overflow: hidden;

		/* margin-bottom: 0; */
		& img {
			/* object-position: top; */
			width: 100%;
			height: 150%;
			object-fit: cover;
			object-position: top;
		}
	}

	.coming-soon-wrapper > :first-child:not(.center) {
		margin-block-start: 0;
	}

	.coming-soon-wrapper > :last-child:not(.center) {
		margin-block-end: 0;
	}

	.coming-soon-wrapper > .center {
		width: 100%;
		margin-block: auto;
	}

	p,
	h2 {
		max-width: 40ch;
		margin-inline: auto;
		margin-inline-start: 0;

		text-align: left;
		text-wrap: balance;
		text-wrap: pretty;
	}
	h2 {
		margin-block-end: 1rem;
		color: var(--c-white);
	}
	p {
		margin-block-end: 2rem;
	}
	.link {
		color: var(--c-yellow);
		text-underline-offset: 3px;
		transition: color 0.2s ease-in-out;
	}
	.link:hover,
	.link:focus-visible {
		color: var(--c-white);
		text-underline-offset: 4px;
	}

	@media (prefers-color-scheme: dark) {
		.coming-soon-wrapper {
			--local-bg-color: var(--c-green);
			--local-font-color: var(--c-white);
			--local-bg-opacity: 0.6;
		}
	}
</style>
