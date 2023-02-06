<h1 class="text-3xl font-bold underline mb-20">Forms</h1>

<div class="mb-10 w-full max-w-md">
	<h1 class="text-2xl font-bold mb-3 text-center">Method GET</h1>
	<form class="flex flex-col gap-y-3" method="GET" action="/login">
		<input class="input input-bordered w-full" placeholder="user" type="text" name="user" />
		<input
			class="input input-bordered w-full"
			placeholder="password"
			type="password"
			name="password"
		/>
		<button class="btn" type="submit">Login</button>
	</form>
</div>

<div class="mb-10 w-full max-w-md">
	<h1 class="text-2xl font-bold mb-3 text-center">Method POST</h1>
	<form class="flex flex-col gap-y-3" method="POST" action="/login">
		<input class="input input-bordered w-full" placeholder="user" type="text" name="user" />
		<input
			class="input input-bordered w-full"
			placeholder="password"
			type="password"
			name="password"
		/>
		<button class="btn" type="submit">Login</button>
	</form>
</div>
