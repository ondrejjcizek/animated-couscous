<script lang="ts">
    type Pokemon = string[] | string;

    function logPokemon(pokemon?: Pokemon): Pokemon {
        if (Array.isArray(pokemon)) {
            return pokemon.map((pokemon) => pokemon.toUpperCase());
        }

        if (typeof pokemon === 'string') {
            return pokemon.toUpperCase();
        }

        return 'Please enter a Pokemon';
    }

    console.log(logPokemon(['Bulbasaur', 'Charmander', 'Squirtle']));

    console.log(logPokemon('Pikachu'));

    console.log(logPokemon());
</script>
