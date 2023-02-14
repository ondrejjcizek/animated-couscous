<script lang="ts">
    type Pokemon = {
        id: number;
        name: string;
        pokemonType: string;
    };

    const pokemon: Pokemon[] = [{ id: 1, name: 'Pikachu', pokemonType: 'electric' }];

    pokemon.forEach((pokemon) => console.log(pokemon));
</script>
