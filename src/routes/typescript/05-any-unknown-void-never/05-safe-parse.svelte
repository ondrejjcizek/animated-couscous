<script lang="ts">
    const json = '{ "id": 1, "name": "Pikachu" }';

    function safeParse(value: string): any {
        return JSON.parse(value);
    }

    const obj = safeParse(json);

    obj.name;
</script>
