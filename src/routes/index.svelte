<script>
    import { pokemon } from '../stores/pokestore';
    import PokemanCard from '../components/card/pokemanCard.svelte'
import { text } from 'svelte/internal';

    let searchQuery = '';
    let filteredPokemon = [];

    // reactivity
    // tribber every time the search gets updates
    $: {
        console.log(searchQuery);
        if(searchQuery) {
            // search the pokemon
            filteredPokemon = $pokemon.filter(pokeman => pokeman.name.toLowerCase().includes(searchQuery.toLowerCase()))
        } else {
            filteredPokemon = [...$pokemon]
        }
    }
</script>

<svelte:head>
    <title>Svelte Kit Pokedex</title>
</svelte:head>

<!-- <h1 class="text-4xl text-center my-8 uppercase">SvelteKit Pokedex</h1> -->
<h1 class="text-4xl text-center my-8 uppercase">SvelteKit Pokedex</h1>

<input class="w-full rounded-md text-lg p-4 border-2 border-gray-500" type="text" bind:value={searchQuery} placeholder="Search for your favorite pokemon">

<div class="py-4 grid gap-4 md:grid-cols-2 grid-cols-1">
    <!-- this gets automatically re-rendered as soon as the store updates/changes -->
    {#each filteredPokemon as pokeman }
        <PokemanCard pokeman={pokeman}/>
    {/each}
</div>