<script lang="ts">
    type LogPokemon = (pokemon: string) => void;

    // named function expression
    const logPokemon1: LogPokemon = function logPokemon(pokemon) {
        console.log(pokemon);
    };

    //  anonymous function expression
    const logPokemon2: LogPokemon = function (pokemon) {
        console.log(pokemon);
    };

    // anonymous arrow function expression
    const logPokemon3: LogPokemon = (pokemon) => {
        console.log(pokemon);
    };

    function logPokemon4(pokemon: string): void {}
    const logPokemon5: LogPokemon = (pokemon) => {};
</script>
