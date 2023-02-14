<script lang="ts">
    const pokemon = [];

    function addPokemon(name: string, timeAdded: Date) {
        pokemon.push({ name, timeAdded });
    }

    addPokemon('Pikachu', new Date());
</script>
