<script lang="ts">
    const apiResponse: unknown = {
        data: []
    };

    const anyType: any = apiResponse;

    const unknownType: unknown = apiResponse;

    const otherType: { data: [] } = apiResponse;

    if (apiResponse && typeof apiResponse === 'object') {
        const response = apiResponse as { data: [] };
        response.data;
    }
</script>
