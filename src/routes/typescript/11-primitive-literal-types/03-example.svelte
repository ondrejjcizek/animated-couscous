<script lang="ts">
    function addPokemon(name: string, pokemonType?: '🔥 fire' | '🌀 water' | '⚡️ electric') {
        console.log({ name, pokemonType });
    }

    const pokemon = {
        name: 'Pikachu',
        pokemonType: '⚡️ electric'
    } as const;

    addPokemon(pokemon.name, pokemon.pokemonType);
</script>
