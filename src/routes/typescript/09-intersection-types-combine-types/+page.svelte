<script lang="ts">
    interface Pokemon {
        name: string;
        hp: number;
        pokemonType: [string, string?];
    }

    interface Ability {
        blaze(): void;
    }

    interface Moves {
        firePunch(): void;
    }

    type Fire = Ability & Moves;

    type FirePokemon = Pokemon & Fire;

    const charizzard: FirePokemon = {
        name: 'Charrizard',
        hp: 100,
        pokemonType: ['type', 'flying'],
        blaze() {
            console.log(`${this.name} used 🔥 Blaze.`);
        },
        firePunch() {
            console.log(`${this.name} used 🔥 Fire Punch.`);
        }
    };

    charizzard.blaze();
    charizzard.firePunch();
</script>
