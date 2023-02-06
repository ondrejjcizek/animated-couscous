<script lang="ts">
	import { invalidateAll } from '$app/navigation';
	import type { PageData } from './$types';

	type Data = {
		success: boolean;
		errors: Record<string, string>;
	};

	let form: Data;

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

<!-- <pre>
    {JSON.stringify(data, null, 2)}
</pre> -->

<div class="max-w-xs">
	<ul class="p-0 flex flex-col gap-y-2">
		{#each data.todos as todo}
			<li class="flex gap-x-3 justify-between items-center">
				<span class="capitalize">{todo.text}</span>
				<form on:submit|preventDefault={removeTodo} method="POST">
					<input type="hidden" name="id" value={todo.id} />
					<button class="btn" type="submit">❌</button>
				</form>
			</li>
		{/each}
	</ul>

	<form class="mt-5 flex gap-x-3" on:submit|preventDefault={addTodo} method="POST">
		<div class="relative">
			<input class="input input-bordered w-full" type="text" name="todo" />
			{#if form?.errors?.todo}
				<p class="status-message bg-rose-600">This field is required</p>
			{/if}
			{#if form?.success}
				<p class="status-message bg-green-600">Added todo! 🥳</p>
			{/if}
		</div>
		<button class="btn" type="submit">+ Add Todo</button>
	</form>
</div>

<style lang="postcss">
	.status-message {
		@apply rounded-lg text-white pointer-events-none text-sm flex items-center justify-center absolute inset-0 h-full w-full;
	}
</style>
