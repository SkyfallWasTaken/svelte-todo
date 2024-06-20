<script lang="ts">
	import Todo from '$lib/Todo.svelte';
	import Plus from 'lucide-svelte/icons/plus';

	let incompleteTodos: string[] = [];
	let completeTodos: string[] = [];

	let currentTodo: string = "";

	function addTodo() {
		incompleteTodos = [currentTodo, ...incompleteTodos];
	}
</script>

<div class="flex flex-col gap-4 p-5">
	<h1 class="text-3xl font-semibold text-white">To-Dos</h1>

	<div class="flex gap-2 rounded-md bg-gray-600 p-2">
		<input
			type="text"
			name="Todo"
            placeholder="Try 'Bake a cake'"
			class="rounded-md bg-gray-700 text-white p-2 shadow-sm"
			bind:value={currentTodo}
		/>
		<button
			on:click={addTodo}
			disabled={currentTodo === ''}
			class="flex gap-1 rounded-md bg-sky-400 p-2 font-semibold shadow-sm transition disabled:bg-slate-500"
		>
			<Plus />
			<p>Add</p>
		</button>
	</div>

	{#each incompleteTodos as todo}
		<Todo {todo} />
	{/each}
</div>
