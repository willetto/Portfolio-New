<script lang="ts">
	import paper from '$lib/imgs/textures/paper2.jpg';

	export let svg: string;
	export let color = '#95bf47';
	export let shape: 'oval' | 'round' | 'square' | 'oblong' = 'oval';
	export let angle: number = 0;
	export let title: string = 'skill';

	// Define different sticker shapes
	const shapes = {
		oval: '48% / 55px',
		round: '50%',
		square: '10px',
		oblong: '50px / 48%'
	} as const;

	// Define different padding values for each shape
	const paddings = {
		oval: '1.75rem 1rem',
		round: '1.75rem',
		square: '1.25rem 1rem',
		oblong: '1.1rem 2rem'
	} as const;

	$: stickerShape = shapes[shape];
	$: stickerPadding = paddings[shape];
</script>

<div
	class="skill"
	style="--sticker-shape: {stickerShape}; --border-color: {color}; --rotation: {angle}deg; --sticker-padding: {stickerPadding}"
>
	<img src={svg} alt={title} {title} class="skill-icon" />
	<img src={paper} class="skill-texture" aria-hidden="true" />
</div>

<style>
	.skill {
		margin: -5px -3px;
		height: fit-content;
		padding: var(--sticker-padding);
		border-radius: 1rem;
		background-color: #f2f0e9;
		border-radius: var(--sticker-shape);
		position: relative;
		box-shadow: 5px 5px 10px -5px rgba(0, 0, 0, 0.5);
		transform: rotate(var(--rotation, 0deg)) scale(1.05);
		transition: transform 0.3s ease-in-out;
	}

	.skill:hover,
	.skill:focus-visible {
		transform: rotate(var(--rotation, 0deg)) scale(1.2);
		/* z-index: 10; */
	}

	.skill:after {
		content: '';
		position: absolute;
		inset: 3px;
		border: 3px solid var(--border-color);
		border-radius: var(--sticker-shape);
	}

	.skill-texture {
		position: absolute;
		inset: 0;
		z-index: 1;
		filter: grayscale(50%) brightness(0.75);
		opacity: 0.5;
		border-radius: var(--sticker-shape);
		object-fit: cover;
		height: 100%;
		width: 100%;
		mix-blend-mode: hard-light;
		pointer-events: none;
	}

	.skill-icon {
		width: 60px;
		height: 60px;
		position: relative;
		z-index: 2;
		object-fit: contain;
	}
</style>
