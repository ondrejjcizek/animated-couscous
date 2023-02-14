<script lang="ts">
    interface Pokemon {
        id: number;
        name: string;
    }

    interface Electric extends Pokemon {
        pokemonType: 'electric';
    }

    const pikachu: Electric = {
        id: 1,
        name: 'Pikachu',
        pokemonType: 'electric'
    };
</script>
