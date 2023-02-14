<script lang="ts">
    const pokemonMissingProperty: { id: number; name: string } = {
        name: 'Pikachu'
    };

    const pokemonOptionalArgument: { id?: number; name: string } = {
        name: 'Pikachu'
    };

    const pokemonExtraProperty: { id?: number; name: string } = {
        id: 1,
        name: 'Pikachu',
        pokemonType: 'electric'
    };
</script>
