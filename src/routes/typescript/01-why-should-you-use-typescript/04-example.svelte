<script lang="ts">
    const pokemon = [];

    function addPokemon(pokemonName: string) {
        if (!pokemonName || typeof pokemonName !== 'string') {
            throw new Error('💩 You have to specify a Pokemon name.');
        }
        pokemon.push(pokemonName);
    }

    // Type 'number' not assignable to type 'string'.  🚫
    addPokemon(1);
</script>
