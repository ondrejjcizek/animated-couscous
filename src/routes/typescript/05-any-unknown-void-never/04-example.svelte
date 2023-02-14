<script lang="ts">
    function prettyPrint(input: unknown): string {
        if (Array.isArray(input)) {
            return input.map(prettyPrint).join(', ');
        }

        if (typeof input === 'string') {
            return input;
        }

        if (typeof input === 'number') {
            return String(input);
        }

        return '...';
    }

    const values = ['Bulbasaur', 'Charmander', 'Squirtle', 1, {}];
    const prettyValues = prettyPrint(values);

    console.log(prettyValues);
</script>
