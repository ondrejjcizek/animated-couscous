<script lang="ts">
    const pokemon: string[] = [];

    const addPokemon = (name: string): string[] => {
        pokemon.push(name);
        return pokemon;
    };

    addPokemon('Pikachu');
</script>
