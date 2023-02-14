<script lang="ts">
    function getPokemonByType(pokemonType: 'fire' | 'water' | 'electric') {
        if (pokemonType === 'fire') {
            return '🔥 Fire Pokemon';
        }

        if (pokemonType === 'water') {
            return '🌀 Water Pokemon';
        }

        if (pokemonType === 'electric') {
            return '⚡️ Electric Pokemon';
        }

        const remainingPokemonTypes: never = pokemonType;

        return remainingPokemonTypes;
    }

    console.log(getPokemonByType('water'));
</script>
