<script lang="ts">
    const pokemon: string[] = [];

    function addPokemon(name: string): string[] {
        pokemon.push(name);
        return pokemon;
    }

    addPokemon('Pikachu');
</script>
