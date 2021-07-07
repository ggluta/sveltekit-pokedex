<script context="module">
    export async function load({page}) {
        const id = page.params.id;
        const url = `https://pokeapi.co/api/v2/pokemon/${id}`
        const response = await fetch(url);
        const pokeman = await response.json();
        return {
            props: {
                pokeman
            }
        }
    }
</script>

<script>
    export let pokeman
    console.log(pokeman)
</script>

<div class="wrapper">
    <h1 class="text-4xl text-center my-8 uppercase">{pokeman.name}</h1>
    <div class="img-wrapper flex justify-center">
        <img class=" h-40 w-40" src={pokeman.sprites['front_default']}>
    </div>
</div>