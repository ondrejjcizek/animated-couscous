<script lang="ts">
    function logPokemon(name: string, hp?: number) {
        console.log({ name, hp });
    }

    // { name: 'Pikachu', hp: undefined }
    logPokemon('Pikachu');

    // { name: 'Pikachu', hp: 35 }
    logPokemon('Pikachu', 35);
</script>
