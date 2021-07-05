<script>
    import { pokemon } from '../stores/pokestore';
</script>

<svelte:head>
    <title>Svelte Kit Pokedex</title>
</svelte:head>

<h1>SvelteKit Pokedex</h1>

// this gets automatically re-rendered as soon as the store updates
{#each $pokemon as pokeman }
    <p>{pokeman.name}</p>
{/each}
