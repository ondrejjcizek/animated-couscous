<script lang="ts">
    interface Pokemon {
        name: string;
        hp: number;
    }

    function logPokemon(name: string, hp: number): void;
    function logPokemon(pokemonObejct: Pokemon): void;

    function logPokemon(arg1: unknown, arg2?: unknown): void {
        if (typeof arg1 === 'string' && typeof arg2 === 'number') {
            console.log(`${arg1} has ${arg2} HP.`);
        }

        if (typeof arg1 === 'object') {
            const { name, hp } = arg1 as Pokemon;
            console.log(`${name} has ${hp} HP.`);
        }
    }

    // Function Overload
    // logPokemon()
</script>
