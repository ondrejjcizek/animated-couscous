<script lang="ts">
    interface Pokemon {
        id?: number;
        name: string;
        pokemonType: string;
        ability: string;
        attack(): void;
    }

    const pokemon = [
        {
            id: 1,
            name: 'Pikachu',
            pokemonType: 'electric',
            abaility: '⚡️ Thunderbolt',
            attack() {
                console.log(`${this.name} used ${this.abaility}`);
            }
        }
    ];

    pokemon.forEach((pokemon) => pokemon.attack());
</script>
