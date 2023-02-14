<script lang="ts">
    type Pokemon = {
        id: number;
        name: string;
    };

    type Electric = Pokemon & { pokemonType: 'electric' };

    const pikachu: Electric = {
        id: 1,
        name: 'Pikachu',
        pokemonType: 'electric'
    };
</script>
