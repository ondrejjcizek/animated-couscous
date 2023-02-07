<script lang="ts">
    import { invalidateAll } from '$app/navigation';
    import type { PageData } from './$types';
    import { fly, fade } from 'svelte/transition';
    import { flip } from 'svelte/animate';

    type Data = {
        success: boolean;
        errors: Record<string, string>;
    };

    let form: Data;
    let messageToShow = false;

    export let data: PageData;

    async function addTodo(event: Event) {
        const formEl = event.target as HTMLFormElement;
        const data = new FormData(formEl);

        const response = await fetch(formEl.action, {
            method: 'POST',
            body: data
        });

        const responseData = await response.json();

        form = responseData;

        formEl.reset();

        await invalidateAll();
    }

    async function removeTodo(event: Event) {
        const formEl = event.target as HTMLFormElement;
        const data = new FormData(formEl);

        const response = await fetch(formEl.action, {
            method: 'DELETE',
            body: data
        });

        await invalidateAll();
    }
</script>

<div class="w-full max-w-xs">
    <ul class="flex h-full flex-col p-0">
        {#each data.todos as todo (todo.id)}
            <li
                in:fly={{ opacity: 0, y: 100, duration: 300 }}
                out:fade={{ duration: 300 }}
                animate:flip={{ duration: 300 }}
                class="line-item mt-1 flex items-center justify-between gap-x-3 border-t-2 border-slate-400/25 pt-1 last:mb-1"
            >
                <span class="capitalize">{todo.text}</span>
                <form on:submit|preventDefault={removeTodo} method="POST">
                    <input type="hidden" name="id" value={todo.id} />
                    <button class="btn" type="submit">❌</button>
                </form>
            </li>
        {/each}
    </ul>

    <div class="submit-floater absolute top-10 left-1/2 -translate-x-1/2">
        <form class="relative flex gap-x-3" on:submit|preventDefault={addTodo} method="POST">
            <input class="input-bordered input w-full" type="text" name="todo" />
            <button class="btn" type="submit">+ Add Todo</button>
            {#if form?.errors?.todo || messageToShow}
                <p
                    in:fly={{ opacity: 0, y: 15, duration: 300 }}
                    out:fade={{ duration: 300 }}
                    class="status-message bg-rose-600"
                >
                    This field is required
                </p>
            {/if}
            {#if form?.success}
                <p
                    in:fly={{ opacity: 0, y: 15, duration: 300 }}
                    out:fade={{ duration: 300 }}
                    class="status-message bg-green-600"
                >
                    Added todo! 🥳
                </p>
            {/if}
        </form>
    </div>
</div>

<style lang="postcss">
    .status-message {
        @apply pointer-events-none absolute top-[125%] flex h-full w-full items-center justify-center rounded-lg text-sm text-white;
    }

    .line-item {
        .btn {
            opacity: 0;
        }

        &:hover {
            .btn {
                opacity: 1;
            }
        }
    }
</style>
