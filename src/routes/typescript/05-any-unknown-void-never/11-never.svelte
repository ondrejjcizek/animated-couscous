<script lang="ts">
    function error(message: string): never {
        throw new Error(message);
    }

    function timeout(ms: number): Promise<never> {
        return new Promise((_, reject) => {
            setTimeout(() => reject(new Error('⌛️ Timed out.')), ms);
        });
    }
</script>
