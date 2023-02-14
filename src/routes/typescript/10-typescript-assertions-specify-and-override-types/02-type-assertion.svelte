<script lang="ts">
    const pokemonInputEl = document.getElementById('input') as HTMLInputElement;

    function handleInput(event: Event) {
        const targetEl = event.target! as HTMLInputElement;
        targetEl.value;
    }

    pokemonInputEl.addEventListener('input', (event) => handleInput);
</script>
