<script context="module" lang="ts">
	export const prerender = true;
</script>

<script lang="ts">
	import { players } from '../data/players';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>Football’s greatest</h1>

	<section class="player-list">
		{#each players as player}
			<article class="player-card">
				<img src="https://source.unsplash.com/random/?footballer" alt="A footballer" />
				<h2>{player.name}</h2>
				<span>{player.position}</span>
				<p>
					Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt
					ut labore et dolore magna aliqua.
				</p>
			</article>
		{/each}
	</section>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
		color: #c57b57;
		font-family: var(--font-hero);
	}

	h2 {
		color: #f7dba7;
		font-size: 30px;
		/* font-family: var(--font-hero); */
	}

	.player-list {
		display: flex;
		gap: 1rem;
		flex-flow: column nowrap;
	}

	.player-card {
		width: 30rem;
		padding: 1rem;
		border-radius: 1rem;
		background-color: var(--primary-color);
		color: white;
		transition: all 0.5s ease-in-out none;
	}
	.player-card:hover {
		outline: auto;
		transform: scale(1.02);
	}

	.player-card p {
		color: inherit;
	}

	.player-card img {
		width: 100%;
		height: 10rem;
		object-fit: cover;
	}
</style>
