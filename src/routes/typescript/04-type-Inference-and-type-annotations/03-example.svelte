<script lang="ts">
    const API = 'https://pokeapi.co/api/v2/pokemon/';

    async function getPokemon(name: string): Promise<{ id: number; name: string }> {
        const response = await fetch(`${API}${name}`);
        const pokemon = await response.json();
        return pokemon;
    }

    async function logPokemon(name: string) {
        const pokemon = await getPokemon(name);
        console.log({ id: pokemon.id, name: pokemon.name });
    }
</script>
