<script lang="ts">
    // https://developer.mozilla.org/en-US/docs/Web/API

    // const formEl = <HTMLFormElement>document.getElementById('form'); Please don't use it
    const formEl = document.getElementById('form') as HTMLFormElement;
    formEl.reset();
</script>
