<script lang="ts">
    const pokemon = [];

    function addPokemon(pokemonName: string) {
        addPokemon(pokemonName);
    }

    // ['Pikachu'] ✅
    addPokemon('Pikachu');

    // Type 'number' not assignable to type 'string'.  🚫
    addPokemon(1);
</script>
