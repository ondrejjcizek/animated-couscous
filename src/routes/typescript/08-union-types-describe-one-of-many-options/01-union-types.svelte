<script lang="ts">
    function logPokemon(pokemon: string[] | string) {
        if (Array.isArray(pokemon)) {
            pokemon.map((pokemon) => pokemon.toUpperCase());
        }

        if (typeof pokemon === 'string') {
            pokemon.toUpperCase();
        }
    }
</script>
