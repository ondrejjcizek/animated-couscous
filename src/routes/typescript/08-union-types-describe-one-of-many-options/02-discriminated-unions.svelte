<script lang="ts">
    interface Fire {
        flamethrower: () => void;
        pokemonType: 'fire';
    }

    interface Water {
        whirlpool: () => void;
        pokemonType: 'water';
    }

    type Pokemon = Fire | Water;

    function pokemonAttack(pokemon: Pokemon) {
        switch (pokemon.pokemonType) {
            case 'fire':
                pokemon.flamethrower();
                break;
            case 'water':
                pokemon.whirlpool();
                break;
        }
    }

    pokemonAttack({
        pokemonType: 'fire',
        flamethrower: () => console.log('🔥 Flamethrower')
    });

    pokemonAttack({
        pokemonType: 'water',
        whirlpool: () => console.log('🌀 Whirlpool')
    });
</script>
