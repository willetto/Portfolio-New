<script lang="ts">
	import drFew from '$lib/imgs/dr-few.png';
	import rule29 from '$lib/imgs/rule29.png';
	import inHire from '$lib/imgs/inhire.png';
</script>

<div class="cards">
	<div class="card">
		<a href="http://www.drfewskincare.com" target="_blank">
			<img class="card-image" src={drFew} alt="Dr. Few Website" />
			<p class="h3">Dr. Few Skincare</p>
			<p class="code">Shopify Custom Theme</p>
			<p class="label">Role: Lead Developer</p>
		</a>
		<p class="label">
			Design Agency: <a class="inline-link" href="https://hellogrip.com/" target="_blank">GRIP</a>
		</p>
	</div>
	<div class="card">
		<a href="http://www.rule29.com" target="_blank">
			<img class="card-image" src={rule29} alt="Rule29 Website" />
			<p class="h3">Rule29 Rebrand</p>
			<p class="code">Headless CMS + SvelteKit</p>
			<p class="label">Role: Lead Developer</p>
			<p class="label">Design Agency: Rule29</p>
		</a>
	</div>
	<div class="card">
		<a href="https://inhire.infolk.co/?email=demo@infolk.co&password=@Test12345" target="_blank">
			<img class="card-image" src={inHire} alt="InHire Website" />
			<p class="h3">InHire App</p>
			<p class="code">SvelteKit + Supabase</p>
			<p class="label">Role: Front-End Developer</p>
			<p class="label">Design Agency: Rule29</p>
		</a>
	</div>
</div>

<style>
	.cards {
		display: flex;
		flex-wrap: wrap;
		gap: 1.5rem;
		width: 100%;
	}

	.cards > * {
		flex-basis: calc((50rem - 100%) * 999);
		flex-grow: 1;
	}

	.cards > :nth-last-child(n + 5),
	.cards > :nth-last-child(n + 5) ~ * {
		flex-basis: 100%;
	}
	.card {
		padding: 1rem;

		text-align: left;

		/* background-color: var(--c-white-o1); */
		backdrop-filter: blur(5px);
		border: 1px solid var(--c-white-o1);
		border-radius: 5px;
		box-shadow: 0 0 30px -10px var(--c-black);

		transition:
			background 0.15s ease-in-out,
			backdrop-filter 0.15s ease-in-out,
			scale 0.15s ease-in-out;
		& a {
			color: inherit;
			text-decoration: none;
		}
		&:hover,
		&:focus {
			scale: 1.01;
			background-color: var(--c-white-o1);
			backdrop-filter: blur(10px);
		}
	}

	.card-image {
		margin-bottom: 1rem;
		border-radius: 3px;
	}

	.code {
		margin-bottom: 1rem;
		font-family: 'Red Hat Mono', 'Courier New', monospace;
		font-size: 1rem;
		line-height: 1.5;
	}

	.label {
		font-family: Georgia, 'Times New Roman', Times, serif;
		font-style: italic;
	}
	a.inline-link {
		padding: 2px 3px;
		text-decoration: underline;
		border-radius: 2px;
		transition:
			color 0.15s ease-in-out,
			background-color 0.15s ease-in-out;
		&:hover,
		&:focus {
			font-style: normal;
			color: #e65737;
			text-decoration: none;
			background-color: var(--c-white);
		}
	}
</style>
