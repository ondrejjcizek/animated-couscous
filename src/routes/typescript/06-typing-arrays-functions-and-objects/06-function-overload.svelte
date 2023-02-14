<script lang="ts">
    function logPokemon(arg1: any, arg2?: any) {
        if (typeof arg1 === 'string' && typeof arg2 === 'number') {
            console.log(`${arg1} has ${arg2} HP.`);
        }

        if (typeof arg1 === 'object') {
            const { name, hp } = arg1;
            console.log(`${name} has ${hp} HP.`);
        }
    }

    // 'Pikachu has 35 HP.'
    logPokemon('Pikachu', 35);

    // 'Pikachu has 35 HP.'
    logPokemon({ name: 'Pikachu', hp: 35 });
</script>
