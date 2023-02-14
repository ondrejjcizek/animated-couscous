<h1 class="text-3xl font-bold text-green-300 underline">Forms</h1>

<nav class="mt-10 mb-20">
    <ul class="flex gap-x-4">
        <li><a class="link-hover link" href="/forms/todos">Todos (JS)</a></li>
        <li><a class="link-hover link" href="/forms/felte">Felte</a></li>
    </ul>
</nav>

<div class="mb-10 w-full max-w-md">
    <h1 class="mb-3 text-center text-2xl font-bold">Method GET</h1>
    <form class="flex flex-col gap-y-3" method="GET" action="/login">
        <input class="input-bordered input w-full" placeholder="user" type="text" name="user" />
        <input
            class="input-bordered input w-full"
            placeholder="password"
            type="password"
            name="password"
        />
        <button class="btn" type="submit">Login</button>
    </form>
</div>

<div class="mb-10 w-full max-w-md">
    <h1 class="mb-3 text-center text-2xl font-bold">Method POST</h1>
    <form class="flex flex-col gap-y-3" method="POST" action="/login">
        <input class="input-bordered input w-full" placeholder="user" type="text" name="user" />
        <input
            class="input-bordered input w-full"
            placeholder="password"
            type="password"
            name="password"
        />
        <button class="btn" type="submit">Login</button>
    </form>
</div>
